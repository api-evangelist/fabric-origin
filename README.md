# Fabric Origin (fabric-origin)

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

Fabric Origin (formerly IVA) is the entertainment data platform powering content discovery experiences for movies, television, games, and trailers. Fabric Origin offers comprehensive entertainment data solutions including metadata, images, trailers, TV listings, and celebrity information through a family of REST APIs. With 30 percent more coverage than other providers and tailored products for every stage of the release cycle, Fabric Origin is an affordable, scalable solution trusted by startups and Fortune 50 companies alike.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/fabric-origin/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/fabric-origin/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Entertainment
- Movies
- Television
- Games
- Trailers
- Metadata

## Timestamps

- **Created:** 2025-03-01
- **Modified:** 2026-04-28

## APIs

### Fabric Origin Entertainment API

The Entertainment API ingests and serves metadata for movies, television shows, and games, including identifiers used to retrieve associated videos and images from sibling APIs. Responses are available in JSON, XML, CSV, and HTML formats via Accept headers or the format query parameter.

- **Human URL:** [https://knowledgebase.fabricdata.com/origin/apis-all/](https://knowledgebase.fabricdata.com/origin/apis-all/)
- **Base URL:** `https://ee.iva-api.com/api/`

#### Tags

- Entertainment
- Metadata
- Movies
- Television
- Games

#### Properties

- [Documentation](https://knowledgebase.fabricdata.com/origin/apis-all/)
- [Knowledge  Base](https://knowledgebase.fabricdata.com/origin)
- [Postman Collection](collections/fabric-origin.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fabric-origin.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fabric Origin Celebrity API

The Celebrity API serves metadata about celebrities, including actors, directors, and other entertainment industry figures, with cross references to titles served by the Entertainment API.

- **Human URL:** [https://knowledgebase.fabricdata.com/origin/apis-all/](https://knowledgebase.fabricdata.com/origin/apis-all/)
- **Base URL:** `https://ee.iva-api.com/api/`

#### Tags

- Celebrities
- People
- Metadata

#### Properties

- [Documentation](https://knowledgebase.fabricdata.com/origin/apis-all/)
- [Postman Collection](collections/fabric-origin.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fabric-origin.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fabric Origin Video API

The Video API generates playable links for trailers and other video assets using video identifiers returned from the Entertainment API, allowing customers to embed Fabric Origin video content into their content discovery experiences.

- **Human URL:** [https://knowledgebase.fabricdata.com/origin/apis-all/](https://knowledgebase.fabricdata.com/origin/apis-all/)
- **Base URL:** `https://ee.iva-api.com/api/`

#### Tags

- Video
- Trailers
- Streaming

#### Properties

- [Documentation](https://knowledgebase.fabricdata.com/origin/apis-all/)
- [Postman Collection](collections/fabric-origin.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fabric-origin.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fabric Origin Image API

The Image API provides access to images hosted on Fabric Origin's servers, including posters, stills, and promotional artwork referenced from the Entertainment and Celebrity APIs. Customers are encouraged to host and serve images from their own infrastructure for production use.

- **Human URL:** [https://knowledgebase.fabricdata.com/origin/apis-all/](https://knowledgebase.fabricdata.com/origin/apis-all/)
- **Base URL:** `https://ee.iva-api.com/api/`

#### Tags

- Images
- Posters
- Artwork

#### Properties

- [Documentation](https://knowledgebase.fabricdata.com/origin/apis-all/)
- [Postman Collection](collections/fabric-origin.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fabric-origin.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Fabric Origin Common Data API

The Common Data API exposes reference data used across the Fabric Origin product family, including country codes, image type lookups, and video type lookups required when working with the Entertainment, Celebrity, Video, and Image APIs.

- **Human URL:** [https://knowledgebase.fabricdata.com/origin/apis-all/](https://knowledgebase.fabricdata.com/origin/apis-all/)
- **Base URL:** `https://ee.iva-api.com/api/`

#### Tags

- Reference Data
- Lookups

#### Properties

- [Documentation](https://knowledgebase.fabricdata.com/origin/apis-all/)
- [Postman Collection](collections/fabric-origin.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fabric-origin.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.fabricdata.com/)
- [Knowledge  Base](https://knowledgebase.fabricdata.com/origin)
- [Solutions](https://knowledgebase.fabricdata.com/origin/solutions)
- [Developer  Portal](https://developer.origin.fabricdata.com/portal/login)
- [Documentation](https://knowledgebase.fabricdata.com/origin/apis-all/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
