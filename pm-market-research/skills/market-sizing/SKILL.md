---
name: market-sizing
description: "Estimate market size — TAM, SAM, SOM — with both top-down and bottom-up approaches, growth projections, and assumptions to validate. Use when sizing an opportunity, building a business case, prepping an investor pitch, or evaluating market entry."
---
# Market sizing (TAM / SAM / SOM)

Triangulates the opportunity from two directions and makes the assumptions explicit, so the numbers are defensible rather than hand-waved.

## Inputs
- The product and market constraints (geography, vertical, customer type). Read attached reports/financials first; use web search for current market data and cite sources.

## Load company context
Read `./company-context/00-company.md` (business model, pricing basis) and `04-market-competitors.md`.

## Method
1. Define the market: problem space, segments, geography, constraints.
2. TAM top-down — start from total industry size and narrow to the relevant slice (with sources).
3. TAM bottom-up — customers × price × frequency — to cross-validate; reconcile the two.
4. SAM — the portion realistically serviceable given product, channels, geography, pricing tier (% of TAM, with reasoning).
5. SOM — achievable share in 1-3 years given competitive position and GTM capacity (% of SAM, with reasoning).
6. Project how TAM/SAM/SOM evolve over 2-3 years; list growth drivers.
7. Number the key assumptions, rate confidence (H/M/L), and say how to validate the most uncertain.

## Output
Save to `./outputs/<YYYY-MM-DD>_market-sizing_<slug>.md`:
```
Market definition: <problem space, boundaries, constraints>
TAM: top-down <…> | bottom-up <…> | reconciled <value>
SAM: <value, % of TAM, why>   SOM: <value, % of SAM, why>
| Metric | Current | 2-3 yr projection |  (TAM / SAM / SOM)
Growth drivers: …
Key assumptions (numbered) + confidence + how to validate
```

## Avoid
- Unsourced numbers, or a single approach — always triangulate top-down vs bottom-up.
- Blurring value-based (revenue) vs volume-based (users/units) sizing — state which.
