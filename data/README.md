# Data Directory

- `raw/`: immutable source snapshots.
- `processed/`: validated tables and the local DuckDB warehouse.
- `tableau/`: final public, dashboard-ready extracts.

Generated data is ignored by Git. Each pipeline will record provenance and
reproduction instructions before any dataset is published.

