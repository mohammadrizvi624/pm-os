---
name: pricing-strategy
description: "Design a pricing strategy — model selection, competitive pricing analysis, willingness-to-pay, price elasticity, tiers and experiments. Use when setting prices, preparing a pricing change, or comparing freemium vs paid. For choosing the revenue model itself, use monetization-strategy first."
---
# Pricing strategy

Sets the price and structure once the revenue model is chosen — grounded in value delivered, competitive position, and willingness to pay.

## Inputs
- The product, the chosen revenue model, and any competitor pricing, survey, or usage data. Read attached files first; research competitor pricing if needed.

## Load company context
Read `./company-context/01-product.md`, `03-users-personas.md`, `04-market-competitors.md` (competitor pricing), `07-tools-stack.md` (for experiments).

## Method
1. Anchor on value: the core value, the customer's alternative and its cost, the quantifiable outcome (time saved, revenue gained, cost cut) → the basis for willingness to pay.
2. Pick the pricing model that fits: flat-rate · per-seat · usage-based · tiered · freemium · freemium+usage · value-based (each suits different products — match to value metric and segment).
3. Analyze competitive pricing: map competitor tiers, find your position (premium/mid/budget) and gaps.
4. Design the structure: 2-4 tiers with clear differentiation, a value metric to charge on, feature gating by value (not arbitrary limits), an anchor tier that's the obvious choice, and an annual discount (typically 15-20%).
5. Estimate sensitivity: Van Westendorp Price Sensitivity Meter if survey data exists (too cheap / cheap / expensive / too expensive), else infer from competitors + value.
6. Plan experiments: A/B pricing pages, founder-led sales conversations, landing-page anchor tests, conversion-by-price cohorts.

## Output
Save to `./outputs/<YYYY-MM-DD>_pricing_<slug>.md`:
```
Recommended model: <…>   | Value metric: <what you charge on>
| Tier | Price | Target segment | Key features | Positioning |
Key assumptions: <assumption> → <how to test>
Risks: <risk> → <mitigation>
```

## Avoid
- Cost-plus or copy-the-competitor pricing detached from value delivered.
- Arbitrary feature gates; gate on value metrics.
- Launching price changes without flagging the assumptions to validate first.
