---
name: fabric-origin-catalog-change-tracking
description: >-
  Keep a local copy of the Fabric Origin catalog current by polling the Entertainment API change-history
  operations, rather than waiting for events Origin Nexus does not emit.
api: Fabric Origin Nexus — Entertainment API
base_url: https://api.origin.fabricdata.com
auth: Ocp-Apim-Subscription-Key header
operations:
  - GetMovieChangeHistoryChangesMoviesHistory_Get
  - GetMovieChangeHistoryWithEntityChangesMoviesHistoryWithEntity_Get
  - GetShowChangeHistoryChangesShowsHistory_Get
  - GetShowChangeHistoryWithEntityChangesShowsHistoryWithEntity_Get
  - GetSeasonChangeHistoryChangesSeasonsHistory_Get
  - GetSeasonChangeHistoryWithEntityChangesSeasonsHistoryWithEntity_Get
  - GetEpisodeChangeHistoryChangesEpisodesHistory_Get
  - GetEpisodeChangeHistoryWithEntityChangesEpisodesHistoryWithEntity_Get
  - GetDbImageChangesImagesIdChanges_Get
source: openapi/fabric-origin-entertainment-api-openapi.yml, openapi/fabric-origin-common-metadata-api-openapi.yml
generated: '2026-09-07'
method: generated
---

# Catalog change tracking

Fabric's guidance is that customers **ingest and cache** Origin Nexus metadata rather than calling it
at request time. That makes staying current your problem, and Origin Nexus gives you a polling
answer, not a push one: there are **no webhooks and no event stream on Nexus**. (Origin *Studio* has
an SNS event surface — different product, different credential. See
`asyncapi/fabric-origin-events-webhooks.yml`.)

## The pattern

Each entity type has a pair of operations that take a date floor and return what changed at or after
it:

| Entity | Ids only | Ids + changed entity |
|---|---|---|
| Movie | `GetMovieChangeHistoryChangesMoviesHistory_Get` | `GetMovieChangeHistoryWithEntityChangesMoviesHistoryWithEntity_Get` |
| Show | `GetShowChangeHistoryChangesShowsHistory_Get` | `GetShowChangeHistoryWithEntityChangesShowsHistoryWithEntity_Get` |
| Season | `GetSeasonChangeHistoryChangesSeasonsHistory_Get` | `GetSeasonChangeHistoryWithEntityChangesSeasonsHistoryWithEntity_Get` |
| Episode | `GetEpisodeChangeHistoryChangesEpisodesHistory_Get` | `GetEpisodeChangeHistoryWithEntityChangesEpisodesHistoryWithEntity_Get` |

Use the `WithEntity` variant when you want to know **what** changed and can act selectively; use the
plain variant when you re-fetch the whole record anyway.

## Loop

1. Persist a watermark per entity type — the timestamp of your last successful poll (UTC).
2. Call the change-history operation with that date floor. Page with `Skip`/`Take`; `Take` is capped
   at 10.
3. For each returned id, re-fetch via `SearchEntertainmentSearch_Get` with `Ids`.
4. Advance the watermark only after the whole page set is durably written. On a 429 or 500, do not
   advance — these operations are reads, so replaying a window is safe and cheap.
5. Image changes for a known image id come from `GetDbImageChangesImagesIdChanges_Get`, which
   returns full history, or partial history from a `From` date.

## Rate reality

Fabric caps automated data changes at **1 per 24 hours per title**, so a daily poll is the natural
cadence — anything tighter mostly re-reads. Core subscriptions start at 25 req/s per API and publish
no rate-limit headers, so pace the loop yourself and back off on 429.

## Watch the taxonomies too

Reference vocabularies move independently of titles and are cheap to refresh:
`GetCommonEnumeratorsGetCommonEnumerators_Get` returns Provider, DeliveryMethod, OfferType and more
in one call, and `GetProvidersGetProviders_Get` is the authoritative provider list. Fabric retires
availability providers in place — iTunes became Apple TV, HBO/Max collapsed into HBOMax, imdbTv was
removed — so a stale provider table silently mis-attributes availability.

## Watch the release notes

Breaking changes are announced only at
<https://knowledgebase.fabricdata.com/origin/release-notes>, with an effective date and no Sunset or
Deprecation response header. There is no feed. If your integration matters, something has to read
that page on a schedule.
