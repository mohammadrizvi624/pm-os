---
name: dashboard-spec
description: "Spec an ongoing KPI dashboard or metrics report — which metrics, segments, comparisons, and alerts to surface for a given audience and decision. Use when designing a dashboard, defining a recurring metrics review, or deciding what to monitor."
---
# Dashboard spec

Defines what an ongoing dashboard should show — anchored to the decision it serves, not "every metric we have" — so it drives action rather than noise.

## Inputs
- The audience, the decision/question the dashboard supports, and the available metrics. Read attached files first.

## Load company context
Read `./company-context/05-metrics-goals.md` (NSM, inputs, guardrails) and `07-tools-stack.md` (BI/analytics tool).

## Method
1. Name the **audience** and the **decision** the dashboard exists to support (exec health-check, team weekly review, launch monitoring).
2. Select metrics top-down: the NSM (or launch metric), its key inputs, and guardrails — pulled from `metrics-framework`. Cut anything that won't change a decision.
3. Define each metric's exact definition, the **cuts/segments**, **time grain**, and **comparisons** (vs prior period, vs target).
4. Set **alerts/thresholds** (when does a number demand attention?).
5. Lay it out top-line → drill-down so the headline reads in seconds.

## Output
Save to `./outputs/<YYYY-MM-DD>_dashboard-spec_<slug>.md`:
```
Audience · decision it serves
| Metric | Definition | Cut/segment | Time grain | Comparison | Alert threshold |
Layout: top-line headline → drill-downs
```

## Avoid
- A metric that won't change a decision — leave it off.
- Numbers with no comparison (a value with no target/trend isn't actionable).
