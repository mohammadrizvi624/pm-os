---
name: metrics-framework
description: "Define the product's measurement model — North Star Metric, the metric tree of inputs that drive it, leading vs lagging indicators, and guardrails — using AARRR or HEART as the lens. Use when deciding what to measure, building a metric tree, or choosing a North Star. (The durable measurement model; quarterly target-setting is pm-execution's okrs.)"
---
# Metrics framework

Builds the durable model of what the product measures and why — a single North Star with the input metrics that move it — so the team optimizes the right things, not vanity numbers.

## Inputs
- The product, its value to users, and the business goal. Read attached files first.

## Load company context
Read `./company-context/01-product.md`, `05-metrics-goals.md` (existing NSM/KPIs), `00-company.md` (business model), and `07-tools-stack.md` (what's instrumentable).

## Method
1. Pick the lens for the product type: **AARRR** (Acquisition · Activation · Retention · Revenue · Referral) for growth/funnel products; **HEART** (Happiness · Engagement · Adoption · Retention · Task-success) for UX/feature quality.
2. Define the **North Star Metric** — one customer-centric measure of delivered value (a leading indicator of business success), not a vanity or pure-revenue number.
3. Build the **metric tree**: decompose the NSM into 3-5 input metrics (the levers the team can actually move), each leading vs lagging noted.
4. Add **guardrail metrics** (things that must not degrade — performance, churn, cost, satisfaction).
5. Map each metric to data availability; flag what isn't instrumented yet (hand to `tracking-plan`).

## Output
Save to `./outputs/<YYYY-MM-DD>_metrics-framework_<slug>.md`:
```
Lens: AARRR | HEART  (why)
North Star Metric: <definition + why it reflects value>
Metric tree: NSM ← input metrics (lever · leading/lagging · owner)
Guardrails: …
Data gaps: <metrics not yet instrumented>
```

## Avoid
- Vanity metrics (raw pageviews, total signups) as the North Star — measure realized value.
- A metric nobody can influence; every input metric needs an owner and a lever.
