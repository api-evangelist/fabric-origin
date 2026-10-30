# Fabric Origin

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Fabric Origin is the entertainment metadata and market-intelligence arm of Fabric, the media software company formed from Xytech and IVA. Origin spans three products: Nexus, a family of 14 REST APIs serving movie, television, game and celebrity metadata plus images, trailers, TV listings, showtimes and licensed third-party ratings from Metacritic, Rotten Tomatoes, Common Sense Media and Katch; Studio, a JSON:API 1.1 metadata management platform with an SNS event surface; and Insights, streaming market intelligence across 1,000+ platforms and 249 countries. Fabric publishes machine-readable OpenAPI 3.1.1 for the whole Nexus surface, an llms.txt index at the company root, and two OAuth-governed hosted MCP servers — Origin Studio and Origin Insights — making it one of the more deliberately agent-ready entertainment-data providers in the catalog.

**Areas:** Entertainment · Metadata · Movies · Television · Games · Celebrities · Trailers · Image · TV Listings · Market Intelligence · Media · MCP

## Fabric Origin on APIs.io

Everything profiled for Fabric Origin is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/fabric-origin/](https://apis.io/providers/fabric-origin/)** — or go straight to one of the APIs or properties below.

### APIs (20)

- [Fabric Origin Entertainment API](https://apis.io/apis/fabric-origin/entertainment-api/) — The Entertainment API ingests and serves metadata for movies, television shows, and games, including identifiers used to retrieve associated videos and…
- [Fabric Origin Celebrity API](https://apis.io/apis/fabric-origin/celebrity-api/) — The Celebrity API serves metadata about celebrities, including actors, directors, and other entertainment industry figures, with cross references to titles…
- [Fabric Origin Video API](https://apis.io/apis/fabric-origin/video-api/) — The Video API generates playable links for trailers and other video assets using video identifiers returned from the Entertainment API, allowing customers…
- [Fabric Origin Image API](https://apis.io/apis/fabric-origin/image-api/) — The Image API provides access to images hosted on Fabric Origin's servers, including posters, stills, and promotional artwork referenced from the…
- [Fabric Origin Entertainment API](https://apis.io/apis/fabric-origin/fabric-origin-entertainment-api/) — The Entertainment API from Fabric Origin — 14 operation(s) for entertainment.
- [Fabric Origin Images API](https://apis.io/apis/fabric-origin/fabric-origin-images-api/) — The Images API from Fabric Origin — 4 operation(s) for images.
- [Fabric Origin Videos API](https://apis.io/apis/fabric-origin/fabric-origin-videos-api/) — The Videos API from Fabric Origin — 2 operation(s) for videos.
- [Fabric Origin Fandango API](https://apis.io/apis/fabric-origin/fandango-api/) — Theatrical showtimes and ticketing — geolocation lookup, nearby theaters, movies playing, and showtime groupings by date, theater, format and amenities,…
- [Fabric Origin Metacritic API](https://apis.io/apis/fabric-origin/metacritic-api/) — Metascores and Metacritic reviews for movies and TV, keyed on Origin identifiers.
- [Origin Studio Production API](https://apis.io/apis/fabric-origin/origin-studio-api/) — The Origin Studio metadata management API — records, record lifecycles, fields, datasets, media, credits, contributors, data deliveries, data ingress,…
- [Origin Studio MCP Server](https://apis.io/apis/fabric-origin/origin-studio-mcp/) — A hosted Model Context Protocol server over Origin Studio — metadata records, catalog operations and availability. Streamable HTTP on the root path, OAuth…
- [Origin Insights MCP Server](https://apis.io/apis/fabric-origin/origin-insights-mcp/) — A hosted Model Context Protocol server over Origin Insights streaming market intelligence — availability, demand, TVOD pricing, subscription plans,…
- [Fabric Origin Analytics API](https://apis.io/apis/fabric-origin/fabric-origin-analytics-api/) — The analytics API from Fabric Origin — 1 operation(s) for analytics.
- [Fabric Origin Common API](https://apis.io/apis/fabric-origin/fabric-origin-common-api/) — The common API from Fabric Origin — 39 operation(s) for common.
- [Fabric Origin Commonsense API](https://apis.io/apis/fabric-origin/fabric-origin-commonsense-api/) — The commonsense API from Fabric Origin — 2 operation(s) for commonsense.
- [Fabric Origin Katchmedia API](https://apis.io/apis/fabric-origin/fabric-origin-katchmedia-api/) — The katchmedia API from Fabric Origin — 1 operation(s) for katchmedia.
- [Fabric Origin Rabbitrecommendations API](https://apis.io/apis/fabric-origin/fabric-origin-rabbitrecommendations-api/) — The rabbitrecommendations API from Fabric Origin — 1 operation(s) for rabbitrecommendations.
- [Fabric Origin Rev API](https://apis.io/apis/fabric-origin/fabric-origin-rev-api/) — The rev API from Fabric Origin — 3 operation(s) for rev.
- [Fabric Origin Rottentomatoes API](https://apis.io/apis/fabric-origin/fabric-origin-rottentomatoes-api/) — The rottentomatoes API from Fabric Origin — 4 operation(s) for rottentomatoes.
- [Fabric Origin Tvgrid API](https://apis.io/apis/fabric-origin/fabric-origin-tvgrid-api/) — The tvgrid API from Fabric Origin — 21 operation(s) for tvgrid.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Fabric Origin Events Webhooks](https://apis.io/asyncapis/fabric-origin/fabric-origin-events-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Fabric Origin MCP Servers](https://apis.io/servers/fabric-origin/fabric-origin-mcp-servers/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Fabric Origin Agentic Access](https://apis.io/agentic-access/fabric-origin/fabric-origin-agentic-access/)

#### Collections (4)

Postman and Open Collection request collections.

- [Fabric Origin Entertainment Data APIs](https://apis.io/collections/fabric-origin/open-fabric-origin/)
- [Fabric Origin Data APIs Entertainment API](https://apis.io/collections/fabric-origin/open-fabric-origin-entertainment-api/)
- [Fabric Origin Data APIs Entertainment Images API](https://apis.io/collections/fabric-origin/open-fabric-origin-images-api/)
- [Fabric Origin Data APIs Entertainment Videos API](https://apis.io/collections/fabric-origin/open-fabric-origin-videos-api/)

#### Overlays (14)

OpenAPI overlays, including conversational phrasing for each operation.

- [Fabric Origin Captions Translations Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-captions-translations-api-overlay/)
- [Fabric Origin Celebrity Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-celebrity-api-overlay/)
- [Fabric Origin Common Metadata Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-common-metadata-api-overlay/)
- [Fabric Origin Common Sense Media Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-common-sense-media-api-overlay/)
- [Fabric Origin Entertainment Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-entertainment-api-overlay/)
- [Fabric Origin Fandango Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-fandango-api-overlay/)
- [Fabric Origin Images Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-images-api-overlay/)
- [Fabric Origin Katch Media Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-katch-media-api-overlay/)
- [Fabric Origin Metacritic Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-metacritic-api-overlay/)
- [Fabric Origin Rabbit Recommendations Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-rabbit-recommendations-api-overlay/)
- [Fabric Origin Rotten Tomatoes Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-rotten-tomatoes-api-overlay/)
- [Fabric Origin Tv Grid Online Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-tv-grid-online-api-overlay/)
- [Fabric Origin Video Analytics Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-video-analytics-api-overlay/)
- [Fabric Origin Videos Api Overlay](https://apis.io/overlays/fabric-origin/fabric-origin-videos-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Fabric Origin Authentication](https://apis.io/security/fabric-origin/fabric-origin-authentication/)
- [Fabric Origin Domain Security](https://apis.io/security/fabric-origin/fabric-origin-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Fabric Origin Scopes](https://apis.io/scopes/fabric-origin/fabric-origin-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Fabric Origin Plans Pricing](https://apis.io/plans/fabric-origin/fabric-origin-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Fabric Origin Rate Limits](https://apis.io/rate-limits/fabric-origin/fabric-origin-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Fabric Origin Finops](https://apis.io/finops/fabric-origin/fabric-origin-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.fabricdata.com/)
- [Documentation](https://knowledgebase.fabricdata.com/origin/apis-all/)
- [Getting started](https://knowledgebase.fabricdata.com/origin/getting-started)
- [API reference](https://knowledgebase.fabricdata.com/origin/apis-all)
- [Pricing](https://www.fabricdata.com/pricing-models)
- [Sign up](https://www.fabricdata.com/contact-us)
- [Support](https://metahive.atlassian.net/servicedesk/customer/portal/2)
- [Blog](https://www.fabricdata.com/trends)
- [Privacy policy](https://www.fabricdata.com/privacy-policy)
- [Status](https://status.fabricdata.com/)

## API Evangelist rating

**Kin Score 55.8** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 49.7 |
| Contract governance | 18.2 |
| Operational transparency | 71.1 |
| Developer ergonomics | 66.1 |
| Access clarity | 42.1 |

**Agent readiness 49.8** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | — |

**Regulatory alignment 35.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/fabric-origin/](https://apis.io/providers/fabric-origin/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Fabric Origin: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/fabric-origin/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
