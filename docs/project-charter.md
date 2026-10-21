# Project Charter

## Problem

Extreme heat can make waiting for public transit hazardous, but citywide heat
maps do not show how temperature combines with waiting time, shade, cooling
access, and the needs of transit-dependent communities at individual stops.

## Objective

Build a reproducible public-data platform that estimates heat exposure at
Phoenix-area transit stops and identifies interventions that could reduce that
exposure fairly and efficiently.

## Primary users

- Transit riders looking for understandable information about heat exposure.
- Transit and city planners prioritizing stop improvements.
- Community organizations planning water and cooling support.
- Journalists and researchers studying heat and transportation equity.

## MVP questions

1. Which stops combine high heat exposure with long scheduled waits?
2. Which high-exposure stops serve communities with limited transportation
   alternatives or greater heat vulnerability?
3. Which routes and neighborhoods contain the largest concentrations of
   priority stops?
4. Which candidate investments could reduce the most rider waiting exposure?

## MVP deliverables

- Documented ingestion and transformation pipeline.
- Versioned DuckDB analytical warehouse.
- Stop-level, route-level, and neighborhood-level Tableau-ready exports.
- Transparent exposure and equity-priority score definitions.
- Public Tableau dashboard and a portfolio case study.

## Initial scope

- Phoenix metropolitan Valley Metro bus service.
- One complete historical hot season, selected after source validation.
- Scheduled service rather than real-time vehicle prediction.
- Public, non-personal data only.

## Out of scope for the first release

- Medical or emergency advice.
- Individual rider tracking.
- A full trip-planning replacement.
- Real-time prediction or alerts.
- Crowdsourced reports without a verification and moderation process.

## Success criteria

- Every published metric has a source, date, definition, and reproducible build
  step.
- Risk scores expose their component measures instead of functioning as a black
  box.
- The dashboard allows a viewer to move from regional patterns to a specific
  stop and understand why it was prioritized.
- A new contributor can reproduce the analytical exports from documented
  commands.

