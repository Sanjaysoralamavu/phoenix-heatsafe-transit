# Public User Questions and Candidate KPIs

## Purpose

This document defines the initial public-facing user questions and candidate KPIs for the Phoenix HeatSafe Transit project.

The project is intended to identify Phoenix-area bus stops where extreme heat, scheduled waiting time, limited cooling access, and community transportation constraints overlap.

The primary public question is:

**Which transit stops expose riders to the greatest heat risk, and where could limited public investment reduce the most exposure?**

These questions and KPIs are initial proposals and may be refined as data sources are validated and analytical methods are finalized.

## Intended Public Users

The dashboard should be understandable to:

- Transit riders and community members
- Transportation planners
- Public agencies
- Community organizations
- Researchers and analysts
- People interested in heat resilience and transit accessibility

## Public User Questions

### 1. Which transit stops have the highest heat exposure?

Users should be able to identify stops where heat conditions, scheduled waiting conditions, and limited cooling or shelter access combine to create higher exposure.

### 2. Why is a particular stop considered high risk?

Users should be able to view the individual components that contribute to a stop's exposure score rather than seeing only a final combined number.

Relevant components may include:

- Heat conditions
- Scheduled waiting conditions
- Shade or shelter availability
- Cooling-resource access
- Service characteristics

### 3. Which stops have longer scheduled waiting conditions?

Users should be able to compare stops based on scheduled transit service and estimated waiting conditions.

Scheduled waiting estimates must not be presented as actual observed rider wait times.

### 4. Which stops have limited access to cooling or shelter resources?

Users should be able to understand whether verified cooling or shelter resources are available near a transit stop.

The dashboard should distinguish between:

- Verified resource availability
- Verified lack of access
- Missing or unavailable data

### 5. Which communities face both high heat exposure and transportation constraints?

Users should be able to compare stop-level exposure with area-level community context.

Candidate community indicators may include:

- Vehicle access
- Age
- Disability
- Poverty
- Transit dependence

These indicators should be treated as area-level context and not as characteristics of individual riders.

### 6. Which routes contain multiple higher-priority stops?

Users should be able to compare routes and identify whether higher exposure or equity-priority conditions are concentrated along particular transit routes.

### 7. How does one stop compare with other stops?

Users should be able to inspect an individual stop and compare its conditions with nearby stops or other stops in the transit network.

The comparison may include:

- Heat conditions
- Scheduled waiting
- Cooling access
- Service frequency
- Community context
- Exposure score
- Equity-priority score

### 8. Which stops could be prioritized under a limited-investment scenario?

Users should be able to explore a transparent investment scenario that ranks potential stop improvements using the project's documented analytical measures.

This should be presented as a planning tool and not as a prediction of actual safety outcomes.

---

## Candidate KPIs

### Heat Conditions

Candidate measures:

- Temperature
- Heat index where available and appropriate
- Afternoon or extreme-heat exposure
- Heat exposure component score

### Scheduled Waiting

Candidate measures:

- Scheduled service frequency
- Estimated scheduled waiting time
- Stops with relatively long scheduled waits

These values should be clearly labeled as schedule-based estimates.

### Shade and Shelter

Candidate measures:

- Shade availability
- Shelter availability
- Missing or unknown shade/shelter status

If reliable shade or shelter data is unavailable, the dashboard should show that limitation rather than assume that the feature is absent.

### Cooling Access

Candidate measures:

- Distance or walking access to a verified cooling resource
- Number of verified cooling resources within the defined access area
- Cooling-access indicator
- Missing resource-data indicator

### Community Context

Candidate measures may include:

- Vehicle access
- Poverty
- Age
- Disability
- Transit dependence

Final variables will depend on the approved Census or ACS data source.

### Service Characteristics

Candidate measures:

- Number of routes serving a stop
- Service frequency
- Scheduled stop activity
- Route-level concentration of higher-priority stops

### Exposure Score

The exposure score should summarize physical heat-related conditions during the selected heat period.

Candidate components include:

- Heat conditions
- Scheduled waiting
- Shade or shelter
- Cooling access

Individual score components should remain visible to the user.

### Equity-Priority Score

The equity-priority score should support comparison of heat exposure with community transportation constraints and heat vulnerability.

It should remain separate from the exposure score.

### Investment Priority

Candidate measures:

- Priority rank
- Exposure score
- Equity-priority score
- Component values used in the ranking
- Scenario assumptions

Any ranking should be presented as an analytical prioritization scenario rather than a guaranteed measure of public benefit.

---

## Dashboard Question Mapping

### Regional Overview

Primary question:

**Where are the highest-priority stops and how are they distributed geographically?**

Candidate KPIs:

- Exposure score
- Equity-priority score
- High-priority stop count
- Stop location
- Route

### Stop Detail

Primary question:

**Why did this stop receive its score?**

Candidate KPIs:

- Heat conditions
- Scheduled waiting estimate
- Shade or shelter status
- Cooling access
- Community context
- Service characteristics
- Exposure-score components
- Equity-priority components

### Route and Equity Comparison

Primary question:

**Which routes and communities contain the largest concentration of higher-priority stops?**

Candidate KPIs:

- Stops by route
- Exposure score by route
- Equity-priority score by route
- Service characteristics
- Community-context indicators

### Investment Priorities

Primary question:

**Which improvements rank highest under a selected investment scenario?**

Candidate KPIs:

- Investment priority rank
- Exposure score
- Equity-priority score
- Scenario assumptions
- Component values

---

## Dashboard Interpretation Rules

The dashboard should follow these principles:

- Keep exposure and equity-priority scores separate.
- Show score components rather than only a single final number.
- Clearly label scheduled waiting values as estimates.
- Distinguish missing data from confirmed absence.
- Present Census or ACS measures as area-level context.
- Avoid medical claims or safety guarantees.
- Avoid presenting investment ranking as a prediction of actual outcomes.
- Display relevant source dates, assumptions, and limitations.
- Use understandable labels and explanatory tooltips.
- Keep the public-facing dashboard interpretable rather than overly complex.

### Initial Priority Measures

The first dashboard version should focus on a limited set of understandable measures:

1. Heat conditions
2. Scheduled waiting conditions
3. Shade or shelter access
4. Cooling-resource access
5. Service characteristics
6. Community context
7. Exposure score
8. Equity-priority score

These measures directly support the project's core public question while preserving transparency and interpretability.