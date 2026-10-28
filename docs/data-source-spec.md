# Data Source Validation Specification

No source should enter the production pipeline until the following information
has been recorded and verified.

## Required metadata

- Official publisher and canonical source page.
- Download or API endpoint.
- License and public redistribution terms.
- Geographic and historical coverage.
- Update frequency and expected publication delay.
- File format, schema, units, and coordinate reference system.
- Stable identifiers and potential join keys.
- Missing-value conventions and known quality limitations.
- Retrieval timestamp and checksum strategy.

## Validation order

1. Valley Metro static GTFS feed.
2. Historical hourly weather observations.
3. Census ACS estimates and tract geography.
4. Cooling-center or hydration-site locations.
5. Shelter, shade, tree-canopy, or defensible proxy data.

## First analytical contract

The first pipeline milestone will create a canonical stop table with one row per
active stop and these minimum fields:

| Field | Description |
| --- | --- |
| `stop_id` | Stable source stop identifier |
| `stop_name` | Public stop name |
| `latitude` | WGS84 latitude |
| `longitude` | WGS84 longitude |
| `route_count` | Number of routes serving the stop |
| `scheduled_arrivals` | Arrivals in the selected service window |
| `average_headway_minutes` | Mean scheduled interval between arrivals |
| `estimated_wait_minutes` | Documented scheduled-wait estimate |
| `service_date_start` | First schedule date represented |
| `service_date_end` | Last schedule date represented |

This contract will be extended only after the transit table passes uniqueness,
coordinate, completeness, and service-date tests.

## Valley Metro static GTFS baseline

- **Publisher:** City of Phoenix Public Transit Department
- **Canonical source:** https://www.phoenixopendata.com/dataset/valley-metro-bus-schedule
- **Download endpoint:** https://www.phoenixopendata.com/dataset/3eae9a4a-98b9-40c8-8df7-8c00c1756235/resource/28ccc0a5-49c8-495c-b91f-193de5ce2cb7/download/googletransit.zip
- **License:** Open Data Commons Attribution License (ODC-By 1.0)
- **Retrieved:** 2026-10-24
- **Local snapshot:** `data/raw/gtfs/2026-10-24/valley_metro_gtfs.zip`
- **Snapshot convention:** `data/raw/gtfs/YYYY-MM-DD/valley_metro_gtfs.zip`
- **SHA-256:** `5fd088231ac2028c28cc5b545b209684558024f456eb7c547db452c6164d8ae6`
- **Feed version:** `GTFS_v4.5_20260914`
- **Service coverage:** 2026-09-28 through 2027-01-24
- **Language:** English
- **Format:** GTFS static ZIP containing CSV text files
- **Coordinates:** WGS84 latitude and longitude
- **Primary join keys:** `stop_id`, `route_id`, `trip_id`, and `service_id`
- **Update frequency:** To be confirmed by observing the official source
- **Raw-data policy:** The downloaded ZIP is excluded from Git and must not be committed

### Validated files

- `agency.txt`
- `routes.txt`
- `trips.txt`
- `stops.txt`
- `stop_times.txt`
- `calendar_dates.txt`
- `transfers.txt`
- `areas.txt`
- `directions.txt`
- `feed_info.txt`
- `frequencies.txt`
- `shapes.txt`
- `stop_areas.txt`

### Validation findings

- The ZIP passed an integrity test with no errors.
- All required project tables are present.
- The feed provides `calendar_dates.txt` but not `calendar.txt`.
- Pipeline service-date logic must therefore support exception-based service
  defined through `calendar_dates.txt`.

