---
description: Decide how to make money and what to charge — revenue model, pricing, or the full chain.
argument-hint: "[model|pricing|full] <product or pricing question>"
---

# /monetize — monetization & pricing

Three modes across the two monetization skills. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/monetize model new API product — revenue options
/monetize pricing move from free to paid
/monetize full our marketplace, end to end
/monetize            # asks which mode
```

## Modes
Parse `$ARGUMENTS` for the mode and the product.
- `model` → **monetization-strategy** (3-5 revenue models with audience fit, unit economics, risks, validation; recommend 1-2 to test).
- `pricing` → **pricing-strategy** (model selection, competitive benchmark, willingness-to-pay / Van Westendorp, tiers, experiments).
- `full` (default) → `model` → `pricing` chain: choose the revenue model, then design pricing for it.
▸ In `full`, checkpoint after the revenue model is chosen before pricing it.

## Pricing output (`pricing` / `full`)
Save to `./outputs/<YYYY-MM-DD>_pricing_<slug>.md`:
```
## Pricing strategy: <product>   (Date · current pricing if any)
Recommended model + why (tied to value delivered)
Pricing structure — | Tier | Price | Includes | Target segment | Key limit |
Free/trial strategy — what's free, what's gated, conversion triggers
Competitive benchmark — | Competitor | Model | Price range | Positioning |
Revenue projections — | Scenario | Assumptions | Y1 | Y2 |  (conservative/expected/optimistic)
Migration plan (if changing pricing) — grandfathering · comms · timeline
Pricing experiments — | Experiment | What we're testing | Method | Duration |
Risks & mitigations — | Risk | Likelihood | Impact | Mitigation |
Metrics to track — conversion by tier, ARPU, upgrade/downgrade, churn by price sensitivity
```

## Next steps
In-plugin/generic: "Validate the assumptions?" → `/analyze scan` or run a pricing experiment. Customer comms for a pricing change happen in marketing; A/B test setup happens in data/analytics.

## Notes
- Pricing is the highest-leverage revenue lever — a small pricing gain beats the same gain in acquisition.
- Value-based beats cost-plus — start from customer value, not your costs.
- Always design a migration path for existing customers on a pricing change.
- References only `pm-strategy` skills.
