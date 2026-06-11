---
description: Run the experiment lifecycle — design a rigorous A/B test, or analyze its results into a ship/extend/stop call.
argument-hint: "[design|analyze] <experiment or results>"
---

# /experiment — experiment lifecycle

Two modes around the test itself: `design` before it runs, `analyze` after. (No `full` — the live test runs between them.) Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/experiment design new onboarding checklist vs control
/experiment analyze Control 4.2% (n=5000), Variant 4.8% (n=5100)
/experiment analyze [upload test results CSV]
/experiment            # asks design or analyze
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `design` → **experiment-design** (hypothesis, primary + guardrails, MDE, sample size/power, duration, pre-registered ship/stop criteria)
- `analyze` → **experiment-analysis** (validate setup → significance + CIs → guardrails → decision)

## Analyze output
```
## A/B results: <test>   (duration · N control/variant)
| Variant | Sample | Metric | Rate | 95% CI |
Stats: relative lift (CI) · p-value · significant? · MDE
Sample-size check: required vs actual → powered / underpowered
Decision: SHIP / EXTEND / STOP — reasoning (statistical + practical)
Business impact if shipped (with confidence) · caveats (SRM, novelty, segments) · follow-up
```
If raw data is provided, run the stats in Python (scipy). Underpowered + flat usually means **extend**, not "no effect".

## Next steps
In-plugin: "Set up post-launch monitoring?" → `/analyze query` or `/measure dashboard`; "Design the follow-up test?" → `design`.

## Notes
- Statistical significance ≠ practical significance — a tiny lift can be significant yet not worth shipping.
- References only `pm-data-analytics` skills.
