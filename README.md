# Datalastic (datalastic)

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

Datalastic is a maritime data API providing real-time AIS vessel tracking, historical ship movements, vessel specifications, and global port data over a simple REST interface. A database of 750,000+ ships is queryable by MMSI, IMO, or UUID for live position, speed, course, heading, destination, and ETA, plus zone traffic monitoring around any coordinate or port, up to 31 days of historical track per request, vessel and port finder search, and asynchronous bulk reports. There is no free tier - access requires a paid subscription (14-day paid trials from EUR 9) with a monthly database-credit model, and every request authenticates with an `api-key` query parameter. All plans share a 600 calls/minute rate limit. The API is documented publicly, so endpoints and parameters can be evaluated before subscribing.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/datalastic/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/datalastic/refs/heads/main/apis.yml)

## Tags

- Vessel Tracking
- Maritime
- AIS
- Ships
- Ports
- Shipping

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Datalastic Live Vessel Tracking API

Real-time AIS position for any ship by UUID, MMSI, or IMO. The `/vessel` endpoint returns location, speed, course, heading, navigational status, destination, and timestamp; `/vessel_pro` adds ETA, actual time of departure, current draft, and UN/LOCODE destination and departure ports; `/vessel_bulk` tracks up to 100 vessels in a single call.

- **Human URL:** [https://datalastic.com/ship-tracking-api/](https://datalastic.com/ship-tracking-api/)
- **Base URL:** `https://api.datalastic.com/api/v0`

#### Tags

- Vessel Tracking
- AIS
- Live Position

#### Properties

- [Documentation](https://datalastic.com/ship-tracking-api/)
- [API Reference](https://datalastic.com/api-reference/)
- [OpenAPI](openapi/datalastic-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/datalastic.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/datalastic.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Datalastic Vessel Traffic in Radius API

Zone traffic monitoring with `/vessel_inradius` - all vessels within a radius (max 50 nautical miles) around a static point (lat/lon, port UUID, or port UN/LOCODE) or a moving vessel (UUID, MMSI, or IMO), with filters for vessel type, subtype, exclusions, and navigational status. `/inradius_history` replays past traffic for the same zones.

- **Human URL:** [https://datalastic.com/api-reference/](https://datalastic.com/api-reference/)
- **Base URL:** `https://api.datalastic.com/api/v0`

#### Tags

- Zone Monitoring
- Port Traffic
- AIS

#### Properties

- [API Reference](https://datalastic.com/api-reference/)
- [OpenAPI](openapi/datalastic-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/datalastic.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/datalastic.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Datalastic Historical Vessel Track API

Historical AIS track for a vessel via `/vessel_history` - past positions filtered by `uuid`, `mmsi`, or `imo` plus a `days` lookback or an explicit `from`/`to` date range (YYYY-MM-DD, maximum 31 days from the `from` date). Each vessel-day of data consumes one credit.

- **Human URL:** [https://datalastic.com/ship-historical-data-api/](https://datalastic.com/ship-historical-data-api/)
- **Base URL:** `https://api.datalastic.com/api/v0`

#### Tags

- Historical Data
- Vessel Tracking
- AIS

#### Properties

- [Documentation](https://datalastic.com/ship-historical-data-api/)
- [API Reference](https://datalastic.com/api-reference/)
- [OpenAPI](openapi/datalastic-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/datalastic.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/datalastic.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Datalastic Vessel Info and Finder API

Static ship data and search. `/vessel_info` returns specifications for a single vessel - MMSI, IMO, country, call sign, type and subtype, gross tonnage, deadweight, TEU, length, breadth, year built, and home port. `/vessel_find` searches the 750,000+ ship database by name (exact or fuzzy), type, subtype, country, tonnage, deadweight, dimensions, and year built.

- **Human URL:** [https://datalastic.com/vessel-finder-api/](https://datalastic.com/vessel-finder-api/)
- **Base URL:** `https://api.datalastic.com/api/v0`

#### Tags

- Ship Specifications
- Search
- Ships

#### Properties

- [Documentation](https://datalastic.com/vessel-finder-api/)
- [API Reference](https://datalastic.com/api-reference/)
- [OpenAPI](openapi/datalastic-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/datalastic.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/datalastic.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Datalastic Port Finder API

Global maritime port data via `/port_find` - search ports by name and get back port name, country ISO code and name, UN/LOCODE, port type, latitude/longitude, and administrative area levels. Port UUIDs and UN/LOCODEs feed directly into the traffic-in-radius endpoints.

- **Human URL:** [https://datalastic.com/api-reference/](https://datalastic.com/api-reference/)
- **Base URL:** `https://api.datalastic.com/api/v0`

#### Tags

- Ports
- Maritime
- Search

#### Properties

- [API Reference](https://datalastic.com/api-reference/)
- [OpenAPI](openapi/datalastic-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/datalastic.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/datalastic.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Datalastic Reports and Usage API

Asynchronous bulk report jobs and account metering. `POST /report` submits a report job and `GET /report` polls its status (PENDING, IN_PROGRESS, DONE) and returns a `result_url` when complete; `report_id=_all` lists all reports. `GET /stat` returns current monthly credit consumption and request statistics at no credit cost.

- **Human URL:** [https://datalastic.com/api-reference/](https://datalastic.com/api-reference/)
- **Base URL:** `https://api.datalastic.com/api/v0`

#### Tags

- Reports
- Usage
- Bulk Data

#### Properties

- [API Reference](https://datalastic.com/api-reference/)
- [OpenAPI](openapi/datalastic-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/datalastic.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/datalastic.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/datalastic/)
- [Website](https://datalastic.com)
- [Documentation](https://docs.datalastic.com/)
- [API Reference](https://datalastic.com/api-reference/)
- [Pricing](https://datalastic.com/pricing/)
- [Plans](plans/datalastic-plans-pricing.yml)
- [Rate Limits](rate-limits/datalastic-rate-limits.yml)
- [Fin Ops](finops/datalastic-finops.yml)
- [Blog](https://datalastic.com/blog/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
