# Datalastic (datalastic)

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
