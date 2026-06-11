---
name: tracking-plan
description: "Design the instrumentation for a feature or funnel — the events, properties, and naming so the metrics are actually measurable. Use when speccing analytics for a launch, defining an event taxonomy, or closing a data gap before you can analyze something."
---
# Tracking plan

Specifies the events and properties to log so a feature/funnel can be measured — the bridge between the metric model and the data warehouse.

## Inputs
- The feature/funnel and the metrics it must support (often from `metrics-framework` or a PRD). Read attached files first.

## Load company context
Read `./company-context/07-tools-stack.md` (analytics tool — Amplitude/Mixpanel/GA/warehouse — and existing conventions), `01-product.md`, and `05-metrics-goals.md`.

## Method
1. Start from the metrics/funnel to measure; work backward to the events needed to compute each.
2. Define each event with a consistent **Object-Action** name (e.g. `checkout_completed`), the trigger (exactly when it fires), and properties (with types).
3. Specify user/account identity and the properties needed for the segment cuts you'll want.
4. Note de-dup/idempotency and a QA step (how you'll verify events fire correctly before trusting the data).

## Output
Save to `./outputs/<YYYY-MM-DD>_tracking-plan_<feature>.md`:
```
| Event | Fires when | Properties (type) | Identity | Metric it supports |
Naming convention · identity model · QA/validation plan
```

## Avoid
- Logging everything — track only what answers a defined metric/question.
- Inconsistent naming or undocumented triggers (the top cause of untrustworthy data).
