---
name: monetization-strategy
description: "Brainstorm 3-5 monetization (revenue-model) options with audience fit, unit economics, risks, and validation experiments. Use when choosing HOW to make money — the revenue model. For setting the actual price/structure, use pricing-strategy."
---
# Monetization strategy

Generates and compares revenue-model options for a product — the "how do we make money" decision, upstream of the "what's the number" pricing decision.

## Inputs
- The product/feature, target segment, and any willingness-to-pay or budget signals. Read attached material; note competitor monetization.

## Load company context
Read `./company-context/00-company.md` (business model, revenue driver), `03-users-personas.md`, `05-metrics-goals.md`.

## Method
Brainstorm 3-5 distinct models from this menu (don't repeat similar ones): freemium · subscription · usage-based · per-seat · one-time purchase · marketplace/transaction fee · advertising. For each:
- How it works for this product (who pays, for what, how often).
- Audience fit — why it resonates with the target customer.
- Unit economics — rough CAC, LTV, break-even, target margin.
- Risks — adoption, price sensitivity, churn, competitive vulnerability, complexity.
- Validation experiment — cheapest test of willingness to pay (survey, landing page, pilot, waitlist) with a success metric.
Then prioritize by strategic fit (revenue/growth/profit goals), ease, and validation potential; recommend 1-2 to test first. Note most products end up hybrid.

## Output
Save to `./outputs/<YYYY-MM-DD>_monetization_<slug>.md`. One block per model:
```
Model: <e.g. usage-based>
How it works: …  | Audience fit: …
Unit economics: CAC ~… · LTV ~… · margin …
Risks: …
Validation: <test> → <success metric>
```
End with: Recommended 1-2 to test first + why.

## Avoid
- Listing near-identical models — force genuine variety.
- Racing to the bottom on price; monitor competitors without copying.
