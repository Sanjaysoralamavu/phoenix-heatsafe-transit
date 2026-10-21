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

