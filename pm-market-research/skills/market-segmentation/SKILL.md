---
name: market-segmentation
description: "Identify 3-5 market-level customer segments with demographics/firmographics, JTBD, pains, and product fit. Use when exploring the addressable market, choosing target audiences, or evaluating new markets (top-down). For clustering your existing users from data, use user-segmentation."
---
# Market segmentation

Defines the distinct customer segments that exist in the market (top-down), so you can choose which to target — distinct from clustering your current users (that's `user-segmentation`).

## Inputs
- The product/market and any market studies or research. Read attached files first; use web research for market data where helpful.

## Load company context
Read `./company-context/00-company.md`, `04-market-competitors.md`, `03-users-personas.md`.

## Method
1. Consider the full addressable market for the product.
2. Pick segmentation dimensions (behavioral, demographic, firmographic, needs-based).
3. Define 3-5 distinct, non-overlapping segments.
4. For each: size & growth, demographics/firmographics, JTBD & desired outcomes, pains/obstacles, desired gains, product fit, and the alternatives they use today.
5. Assess opportunity per segment (size, growth, competitive intensity) and flag which need more research.

## Output
Save to `./outputs/<YYYY-MM-DD>_market-segments_<slug>.md`. Per segment (3-5):
```
Segment: <name>  | Size/%: …  | Growth: …
Demographics/firmographics: …
JTBD & outcomes: …  | Pains: …  | Gains: …
Product fit: …  | Current alternatives: …
Opportunity: <size × growth × competitive intensity>
```

## Avoid
- Overlapping or non-measurable segments.
- Demographics alone — anchor on JTBD and needs.
