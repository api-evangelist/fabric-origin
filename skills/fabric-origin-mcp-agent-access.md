---
name: fabric-origin-mcp-agent-access
description: >-
  Connect an agent to Fabric's two Origin MCP servers — Origin Studio (metadata records and catalog
  operations, read/write) and Origin Insights (streaming market intelligence, read-only) — and operate
  them safely given that neither exposes an idempotency key.
api: Fabric Origin MCP
endpoints:
  - https://mcp-api.studio.fabricdata.com
  - https://insights.fabric-mcp.link
auth: OAuth 2.0 authorization code + PKCE (S256); API key bearer accepted on Origin Studio
operations:
  - whoami
  - create_api_key
source: mcp/fabric-origin-mcp.yml, authentication/fabric-origin-authentication.yml, conventions/fabric-origin-conventions.yml
generated: '2026-09-07'
method: generated
---

# Connecting an agent to Fabric Origin over MCP

Fabric ships two hosted MCP servers in the Origin family. Both are Streamable HTTP, both implement
the MCP authorization spec, and both let a spec-compliant client discover everything it needs with no
out-of-band configuration.

| | Origin Studio | Origin Insights |
|---|---|---|
| Endpoint | `https://mcp-api.studio.fabricdata.com` | `https://insights.fabric-mcp.link` |
| Covers | metadata records, catalog operations, availability | availability, demand, pricing, plans, platforms, reports |
| Writes | **yes** | no — read-only |
| Auth | OAuth+PKCE, or an API key as bearer | OAuth, browser sign-in |

## Connect

Origin Studio, Claude Code:

```
claude mcp add --transport http origin-studio https://mcp-api.studio.fabricdata.com
```

No headers. The client reads `/.well-known/oauth-authorization-server`, registers itself at the
server's own `/register`, and runs the browser flow.

Origin Insights: add `https://insights.fabric-mcp.link` as a custom connector, or use the
first-party installer at <https://download.fabric-mcp.link/>.

**Do not hard-code Auth0 URLs for Origin Studio.** The MCP server is its own authorization server and
brokers Auth0 internally; Auth0's own registration endpoint will reject you. Take every endpoint from
the discovery document.

## Unattended access

For jobs with no human, send an Origin Studio API key as the bearer token. The server treats any
non-JWT bearer as an API key. There is **no client-credentials flow** for third parties.

If you request `offline_access`, note the refresh token is **long-lived and non-rotating** — the same
token stays valid across exchanges. Encrypt at rest and revoke on offboarding.

## Operate

1. **Start with `whoami`.** It returns the active identity, tenant and effective permissions.
   Permissions are the Studio user's own — an agent can never exceed them — so two users on the same
   agent legitimately see different results.
2. **Never pass a tenant.** Tenant is derived from the token; client-supplied hints are ignored.
   Users belonging to several organizations pick one at sign-in, and the client cannot pre-select.
3. **`find_*` is safe to retry.** Read-only, no side effects.
4. **Writes have no idempotency key.** Fabric's own instruction is to re-query and check whether a
   timed-out write landed before resending. Follow it literally: read-back, then retry. There is no
   `Idempotency-Key` header on this surface and no documented replay window.
5. **Resolve keys before writing.** Metadata fields and dataset values are tenant-specific. Fetch the
   valid keys from the reference catalogs exposed via `resources/list` rather than guessing.
6. **Lifecycle is transitions, not edits.** Read a record's available transitions and apply one; do
   not try to set a state through a metadata update.
7. **File imports upload client-side.** The server issues a presigned URL and your client uploads
   directly — file contents never pass through the agent.

## Reversibility

Fabric documents **no** cancel, undo, rollback or restore operation and states no reversal window
anywhere in the public Origin Studio documentation. Treat every Studio write as one-way until you
have confirmed otherwise with your account team, and keep destructive operations behind a human
approval checkpoint — Fabric's governance model supports exactly that.

## Reading Origin Insights

Ask business questions, not queries. One `action` per call; feed the result forward.

```
titles       { action: "find_title", keyword: "..." }            -> uid
demand       { action: "measure_title_popularity", ... }         -> trend vs market
availability { action: "find_where_to_watch", uid: "..." }       -> platforms + business model
reports      { action: "generate_title_report", uid: "..." }     -> one visual report
```

`execute_sql` and `query_raw_data` exist but are a last resort; call `list_tables` and
`get_table_schema` first if you use them. When a title is ambiguous the tool returns a candidate list
instead of data — pick one and call again. When something is absent the answer says so verbatim
rather than inventing it.

## Troubleshooting

| Symptom | Cause |
|---|---|
| `401` + `WWW-Authenticate` | No token or expired. Refresh, or re-run the flow |
| `403 Origin not allowed` | Browser client, non-allowlisted `Origin`. Ask Fabric to allowlist it |
| `invalid_client` at `/authorize` | Unknown or expired `client_id` |
| `redirect_uri does not match` | Exact-match only — no wildcards, no differing paths |
| DCR rejected at `/oidc/register` | You called Auth0, not the MCP server |
| HTML instead of JSON | Wrong hostname |
