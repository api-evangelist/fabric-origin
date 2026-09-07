---
name: fabric-origin-showtimes-and-ticketing
description: >-
  Build a theatrical showtimes and ticketing experience with the Fabric Origin Fandango API — resolve a
  location, find nearby theaters and playing movies, and pull showtime groupings linked back to Origin
  title identifiers.
api: Fabric Origin Nexus — Fandango API
base_url: https://api.origin.fabricdata.com
auth: Ocp-Apim-Subscription-Key header
operations:
  - GetFandangoGeoLocationPostalCodeGeoLocationByPostalCode_Get
  - GetFandangoGeoLocationCityGeoLocationByCity_Get
  - GetFandangoTheatersTheaters_Get
  - GetFandangoMoviesMovies_Get
  - GetFandangoShowtimesShowtimes_Get
  - GetFandangoTheaterShowtimeGroupingsTheatershowtime-groupings_Get
  - GetFandangoMovieShowtimeGroupingsMovieshowtime-groupings_Get
  - GetFandangoTheaterDisplayDatesTheaterdisplay-dates_Get
  - GetFandangoMovieDisplayDatesMoviedisplay-dates_Get
  - GetFandangoMovieByIdMovieById_Get
  - GetFandangoTheaterTheaterById_Get
  - GetFandangoShowtimeByIdShowtimeById_Get
source: openapi/fabric-origin-fandango-api-openapi.yml
generated: '2026-09-07'
method: generated
---

# Showtimes and ticketing

The Fandango API is an add-on included with the **Movie Showtimes and Ticketing** solution. It sits
on the same host and the same subscription key as the rest of Origin Nexus, and its records carry
Origin identifiers so you can pull posters, trailers and metadata for anything showing.

## 1. Resolve a location

Everything geographic starts here.

- Postal code → `GetFandangoGeoLocationPostalCodeGeoLocationByPostalCode_Get`
  (`/Fandango/GeoLocation/ByPostalCode?country=US&postalcode=08033`)
- City → `GetFandangoGeoLocationCityGeoLocationByCity_Get`
  (`/Fandango/GeoLocation/ByCity?country=US&State=NJ&City=haddonfield`)

## 2. Find what is playing

- `GetFandangoTheatersTheaters_Get` — theaters near a geolocation.
- `GetFandangoMoviesMovies_Get` — movies currently available.
- `GetFandangoTheaterDisplayDatesTheaterdisplay-dates_Get` /
  `GetFandangoMovieDisplayDatesMoviedisplay-dates_Get` — which dates actually have showtimes, so you
  do not query empty days.

## 3. Pull showtimes

Two shapes, pick by the axis your UI is built on:

- Theater page → `GetFandangoTheaterShowtimeGroupingsTheatershowtime-groupings_Get`, grouped by date,
  movie, format and amenities.
- Movie page → `GetFandangoMovieShowtimeGroupingsMovieshowtime-groupings_Get`, grouped by date,
  theater, format and amenities.
- Flat list → `GetFandangoShowtimesShowtimes_Get` by geolocation/theater and date.

Single-record lookups: `GetFandangoMovieByIdMovieById_Get`, `GetFandangoTheaterTheaterById_Get`,
`GetFandangoShowtimeByIdShowtimeById_Get`. These take `idprovider=fandangoapi` alongside the id.

## 4. Enrich with Origin metadata

Fandango records link to Origin title identifiers. Feed those into
`SearchEntertainmentSearch_Get` with `Ids` to pull synopsis, cast and characteristics, then into the
Image and Video APIs for a poster and a trailer. See
`skills/fabric-origin-title-lookup-and-enrichment.md`.

## Gotcha: the January 2026 path rename

Every Fandango path was renamed in the 2026-01-05 AWS migration — `/Fandango/movies/Id` became
`/Fandango/Movie`, `/Fandango/theaterbyid/{TheaterId}` became `/Fandango/TheaterById`, and so on for
nine endpoints. The operationIds above match the **current** spec. If you are reading older
integration code or an older copy of the contract, check it against
<https://knowledgebase.fabricdata.com/origin/release-notes>, which publishes the full old-path →
new-path table. There is no redirect and no Sunset header; old paths simply stop resolving.

## Constraints

Read-only, `Take` capped at 10, no rate-limit headers, 429 on throttle. Showtime data is
time-sensitive — cache it for minutes, not days, and always re-resolve before sending a user to a
ticketing link.
