---
name: fabric-origin-title-lookup-and-enrichment
description: >-
  Resolve a movie, show, season, episode or game to a Fabric Origin identifier and pull its full
  enrichment set — metadata, images, trailers and third-party ratings — using the Origin Nexus
  Entertainment, Image, Video, Metacritic and Rotten Tomatoes APIs.
api: Fabric Origin Nexus
base_url: https://api.origin.fabricdata.com
auth: Ocp-Apim-Subscription-Key header
operations:
  - SearchEntertainmentSearch_Get
  - MatchToEntertainmentProgramMatch_Get
  - GetEntertainmentMatchCandidatesGetEntertainmentMatchCandidates_Get
  - GetImageBatchBatch_Post
  - GetVideoGetVideoId_Get
  - GetClosedCaptionClosedCaptionsVideoId_Get
  - GetMetacriticMovieMovieId_Get
  - GetRottenTomatoesMovieMovie_Get
source: openapi/fabric-origin-entertainment-api-openapi.yml, openapi/fabric-origin-images-api-openapi.yml, openapi/fabric-origin-videos-api-openapi.yml, openapi/fabric-origin-metacritic-api-openapi.yml, openapi/fabric-origin-rotten-tomatoes-api-openapi.yml
generated: '2026-09-07'
method: generated
---

# Title lookup and enrichment

Origin Nexus is title-centric and **read-only**. Everything hangs off one identifier of the form
`Type/Number` (for example `Movie/123`). Get that identifier right and every other call is a lookup.

## Before you start

- Send `Ocp-Apim-Subscription-Key: <key>` as a **header**. The `subscription-key` query parameter
  works but ends up in intermediary logs — prefer the header.
- `Take` is capped at **10**. A larger value returns `400 Bad Request` (changed 2026-02-10). Page
  with `Skip`.
- Send `Accept-Encoding: gzip`. Responses are large and the gateway drops anything over 10MB with a
  **500 that looks like a server fault but is a paging problem**.
- There are **no rate-limit response headers**. You cannot read remaining quota; count your own
  requests. Core subscriptions start at 25 req/s per API; a free trial is 5 req/s and 1,000/month.

## 1. Resolve the title

Prefer a match over a search when you already have structured fields.

- Known title + year + cast/director → `MatchToEntertainmentProgramMatch_Get`
  (`GET /Entertainment/Match/`). Returns the best single match.
- Ambiguous input → `GetEntertainmentMatchCandidatesGetEntertainmentMatchCandidates_Get`
  (`GET /Entertainment/GetEntertainmentMatchCandidates`). Returns a candidate list; pick one, do not
  guess.
- Free-text discovery → `SearchEntertainmentSearch_Get` (`GET /Entertainment/Search/`) with `Ids`,
  `Skip`, `Take` and the type filter. Read `Total` in the response before paging.
- Season or episode by position → `MatchToEntertainmentSeasonBySequenceMatchSeasonBySequence_Get`
  and `MatchToEntertainmentEpisodeBySequenceMatchEpisodeBySequence_Get`.

Both Search and Match have `_Post` twins for long parameter sets. They are the same operation with a
body instead of a query string — no idempotency semantics attach to either.

## 2. Pull images

Image identifiers arrive on the entertainment record. Batch them:

- `GetImageBatchBatch_Post` (`POST /Images/Batch`) for many at once.
- `GetImageRedirectFilePathRedirect_Get` returns a redirect to a single image.

**The Image API is capped at 50 calls per month.** Fabric's standing instruction is to cache images
and serve them from your own infrastructure. Treat the Image API as an ingestion tool, never as a
runtime CDN.

## 3. Pull video

- `GetVideoGetVideoId_Get` (`GET /Videos/GetVideo/{Id}`) takes a `VideoId` from the entertainment
  record and returns a **signed redirect URL**. Signed URLs expire — fetch one at play time, do not
  cache the URL.
- `HlsNoAudioOnly=true` (added 2026-09-02) excludes the audio-only fallback track so the lowest
  rendition always carries video.
- `GetClosedCaptionClosedCaptionsVideoId_Get` returns a WebVTT file for that video.

Unlike metadata and images, video is served from Fabric's CDN direct to the end user unless the
contract says otherwise.

## 4. Layer third-party ratings

Use the same Origin identifier as the join key. Each of these is a separate licensed add-on — a 403
here means the solution bundle does not include it, not that the title is missing.

- `GetMetacriticMovieMovieId_Get` / `GetMetacriticTvTVId_Get`
- `GetRottenTomatoesMovieMovie_Get`, `...ShowShow_Get`, `...SeasonSeason_Get`, `...EpisodeEpisode_Get`
- Common Sense Media and Katch Media have their own APIs on the same identifier.

## Errors you will actually hit

| Code | Meaning here |
|---|---|
| 400 | Almost always `Take` > 10 |
| 403 | Missing key, or the operation is outside your solution bundle |
| 429 | Throttled — no headers tell you how long, back off exponentially |
| 500 | Frequently the 10MB gateway ceiling, not a fault. Reduce `Take`, enable gzip |

## What this API will not do

There is no write path, no idempotency key and nothing to reverse — every operation is a read. There
is also no webhook for Nexus; to track change, poll the change-history operations
(`GetMovieChangeHistoryChangesMoviesHistory_Get` and its Show/Season/Episode siblings) with a date
floor. See `skills/fabric-origin-catalog-change-tracking.md`.
