---
name: metric-investigation
description: "Root-cause a metric move — 'why did activation drop 8% last week?' Check data integrity, decompose and segment, rule causes in/out, and land on the likely explanation with a confidence level. Use when a metric shifts unexpectedly or you need to diagnose a change before reacting."
---
# Metric investigation

A disciplined diagnosis of why a metric moved, so the team reacts to the real cause rather than the first plausible story.

## Inputs
- The metric, the size and timeframe of the move, and access to the data (or a description of it). Read attached files first; generate a query/script if raw data is provided.

## Load company context
Read `./company-context/05-metrics-goals.md` (metric definition), `07-tools-stack.md` (and any release/deploy log), and `04-market-competitors.md` (external/seasonal factors).

## Method
1. Confirm the metric's exact definition, the magnitude, and the window — is the move even outside normal variance?
2. **Check data integrity first** — a logging/instrumentation/definition change is the most common false alarm. Rule it out before anything else.
3. Decompose: the metric as a formula (e.g. rate = numerator/denominator — which moved?); segment by dimension (new vs existing, platform, geo, source, cohort) to localize the move.
4. Line up candidate causes — internal (a release, pricing/UX change, marketing push) vs external (seasonality, competitor, macro) — and rule each in or out against the segment evidence.
5. State the **likely cause with a confidence level**, what would confirm it, and the recommended action (or "monitor").

## Output
Save to `./outputs/<YYYY-MM-DD>_metric-investigation_<metric>.md`:
```
Move: <metric> <Δ> over <window> (vs normal variance?)
Data integrity: <ruled out / suspect>
Decomposition + segment localization: <where the move concentrates>
Causes ruled in / out (with evidence)
Likely cause: <…> (confidence H/M/L) · what would confirm · recommended action
```

## Avoid
- Jumping to a cause before ruling out an instrumentation change.
- A single explanation with no confidence level or confirming check.
