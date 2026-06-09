---
description: Stand up measurement — define the metric model, instrument it, and spec the dashboard to monitor it.
argument-hint: "[framework|tracking|dashboard|full] <product or feature>"
---

# /measure — stand up measurement

Routes a single setup skill, or `full` chains the three end to end (model → instrument → monitor). Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/measure full our activation funnel
/measure framework the whole product
/measure tracking the new checkout flow
/measure dashboard exec weekly health
/measure            # asks what you're measuring
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `framework` → **metrics-framework** (NSM + metric tree + guardrails)
- `tracking` → **tracking-plan** (events/properties to instrument it)
- `dashboard` → **dashboard-spec** (what to monitor)
- `full` (default) → framework → tracking → dashboard.

## Workflow (`full`)
1. **metrics-framework**: define the NSM, input metrics, and guardrails. ▸ Checkpoint: confirm the North Star before instrumenting.
2. **tracking-plan**: the events/properties needed to compute those metrics; flag any data gaps.
3. **dashboard-spec**: the dashboard that surfaces the NSM, inputs, and guardrails for the audience.

## Next steps
In-plugin: "Start reading the data?" → `/analyze`; "Test a lever?" → `/experiment`.

## Notes
- The metric tree should ladder to the same outcomes as `pm-execution`'s OKRs — this is the durable measurement model, not the quarterly target.
- References only `pm-data-analytics` skills.
