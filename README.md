# Phoenix HeatSafe Transit

Phoenix HeatSafe Transit is a public-interest data engineering and analytics
project that identifies bus stops where extreme heat, long waits, limited
cooling resources, and community vulnerability overlap.

The project will produce a reproducible data pipeline, a documented heat-risk
model, and a public Tableau dashboard that helps riders, planners, journalists,
and community organizations understand where heat-mitigation investments could
have the greatest impact.

## Public question

> Which Phoenix-area transit stops expose riders to the greatest heat risk,
> and where could limited public investment reduce the most exposure?

## Planned product

- A stop-level analytical dataset built from public transit, weather,
  demographic, and cooling-resource data.
- Separate, explainable exposure and equity-priority scores.
- An interactive Tableau Public dashboard with a stop map, route and
  neighborhood filters, time-based risk views, and an investment-priority
  table.
- A scenario model that estimates the benefit of adding shade, water, cooling
  access, or more frequent service.
- Reusable exports for researchers and community organizations.

## Architecture

```text
Public data sources
        |
Python ingestion and validation
        |
Raw, processed, and analytics-ready layers
        |
DuckDB analytical warehouse
        |
Risk and recommendation models
        |
Tableau extract / public dashboard
```

See [docs/architecture.md](docs/architecture.md) for the evolving technical
design.

## Repository layout

```text
config/       Data-source and project configuration
dashboard/    Tableau design notes and publishing checklist
data/         Local raw, processed, and Tableau-ready data
docs/         Charter, architecture, methodology, and source documentation
models/       Analytical SQL and risk-model definitions
pipelines/    Ingestion and transformation entry points
src/          Reusable Python package
tests/        Automated data and code tests
```

Large datasets and Tableau workbook artifacts are excluded from Git by
default. Small, publishable samples may be added later with clear provenance.

## Local setup

Python 3.11 or newer is recommended.

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -e ".[dev]"
pytest
```

## Delivery roadmap

1. Validate source availability, licensing, geographic coverage, and join keys.
2. Build the canonical Valley Metro stop and service-frequency dataset.
3. Add historical heat exposure and Census indicators.
4. Add cooling-resource proximity and document data limitations.
5. Develop and validate the transparent risk-scoring methodology.
6. Export a Tableau-ready star schema and create the public dashboard.
7. Add the investment scenario model, deployment documentation, and portfolio
   case study.

## Current status

Repository foundation created. Source validation and the first stop-level data
pipeline are the next milestone.

## Data ethics

This project will use public, non-personal data. Community characteristics will
be used to prioritize resources, not to characterize people or neighborhoods as
dangerous. Scores will expose their component measures, assumptions, data dates,
and uncertainty. The dashboard will be an analytical planning tool, not medical
or emergency guidance.

