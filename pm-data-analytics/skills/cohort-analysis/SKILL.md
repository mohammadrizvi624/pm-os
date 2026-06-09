---
name: cohort-analysis
description: "Analyze user behavior by cohort — retention curves, feature-adoption trends, and engagement over time — then recommend follow-up research. Use when studying retention by signup cohort, churn patterns, feature adoption, or why one cohort under/over-performs."
---
# Cohort analysis

Groups users by a shared start (signup month, feature-launch date) and tracks how a metric evolves per cohort, surfacing retention and adoption patterns — then points to the qualitative follow-up that explains them.

## Inputs
- Cohort data (CSV/Excel/JSON) with a cohort identifier, time periods, and engagement/retention metrics. Read attached files first; validate structure and flag data-quality issues. Generate a pandas script for reproducible analysis if useful.

## Load company context
Read `./company-context/05-metrics-goals.md`, `01-product.md`, and any release/event notes that explain cohort differences.

## Method
1. Validate the data; summarize cohort sizes, date range, and available metrics.
2. Compute retention/engagement per cohort over time; build a retention curve and a cohort × period view (heatmap-ready).
3. Spot patterns: early churn, late-stage changes, adoption clusters, seasonal/temporal effects, and anomalies vs a baseline.
4. Tie deviations to product changes or events in the period where known.
5. Recommend follow-up research: interviews with churned users from a weak cohort, usage surveys with strong cohorts, session replays, or an experiment.

## Output
Save to `./outputs/<YYYY-MM-DD>_cohort-analysis_<slug>.md`:
```
Data summary: cohorts · range · metrics · quality notes
Retention/engagement by cohort (curve + cohort×period table)
2-3 significant patterns (with likely driver if known)
Recommended follow-ups (qual + quant)
```

## Avoid
- Reading patterns from too few/too-small cohorts — flag low-n.
- Reporting curves without a "so what" — every pattern needs a recommended next step.
