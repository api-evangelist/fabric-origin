# Fabric Origin (fabric-origin)

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
