---
name: funnel-analysis
description: "Analyze a conversion funnel — step-by-step conversion and drop-off, where users leak, and the likely why. Use when diagnosing onboarding/activation/checkout drop-off, finding the biggest conversion leak, or comparing funnel performance by segment."
---
# Funnel analysis

Finds where users fall out of an ordered path to an outcome and turns the biggest leak into a prioritized hypothesis — the quantitative complement to a journey map.

## Inputs
- The funnel definition and event/conversion data (counts per step, ideally segmentable). Read attached files first; generate a Python/SQL script if raw data is provided.

## Load company context
Read `./company-context/05-metrics-goals.md` (the conversion outcome that matters) and `03-users-personas.md`.

## Method
1. Define the funnel as ordered steps to the outcome; confirm each step maps to a real event.
2. Compute per-step conversion, step-to-step drop-off, and overall conversion.
3. Find the **biggest leak** (largest absolute user loss, not just lowest rate).
4. Segment the leak (new vs returning, platform, source, persona) to see *who* drops.
5. Form falsifiable hypotheses for the leak and recommend the next probe (a `metric-investigation`, a test, or qual follow-up).

## Output
Save to `./outputs/<YYYY-MM-DD>_funnel_<slug>.md`:
```
| Step | Users | Step conversion | Cumulative | Drop-off |
Biggest leak: <step> (<N users lost>)
By segment: <who drops hardest>
Hypotheses (ranked) → recommended next probe
```

## Avoid
- Optimizing the lowest-rate step when a higher-volume step loses more users.
- Stopping at "where" — push to a testable "why".
