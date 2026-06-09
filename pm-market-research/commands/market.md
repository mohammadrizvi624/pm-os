---
description: Market intelligence — segment the market, size it (TAM/SAM/SOM), analyze competitors, or scan all three.
argument-hint: "[segments|sizing|competitors|scan] <product, market, or industry>"
---

# /market — market intelligence

Routes to a single market analysis, or `scan` chains all three into a market-opportunity brief. Underlying skills load `./company-context/*`, use web research for current data, and save to `./outputs/`.

## Invocation
```
/market scan EdTech for corporate learning — market entry
/market segments our analytics platform
/market sizing API product, US mid-market
/market competitors Notion, Asana, Monday vs us
/market            # asks which analysis
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `segments` → **market-segmentation** (top-down market segments — not your existing users; that's `/research-users segment`)
- `sizing` → **market-sizing** (TAM/SAM/SOM, top-down + bottom-up)
- `competitors` → **competitor-analysis** (landscape + differentiation)
- `scan` → segments → sizing → competitors, synthesized.

## Competitors output (`competitors` / `scan`)
```
Market overview: <dynamics, trends, where it's heading>
Landscape — | Competitor | Category | Target | Positioning | Strength | Weakness |
Feature comparison — | Capability | Us | A | B | C |
Differentiation opportunities (defensible & valuable) · Competitive threats (+ response)
Recommendations: double down on … · close the gap on (table stakes) … · ignore …
```
Distinguish table stakes (needed to compete) from differentiators (needed to win).

## Scan output
Save to `./outputs/<YYYY-MM-DD>_market-opportunity_<slug>.md`:
```
## Market opportunity: <market>   (Date · purpose)
Executive summary
Segments — 3-5, with size/growth/JTBD/fit
Sizing — TAM/SAM/SOM table (current + 2-3yr) with key assumptions
Competitors — landscape table + differentiation opportunities
Synthesis — best segment × realistic SOM × where to differentiate
Recommendation + the assumptions to validate first
```

## Next steps
In-plugin/generic: "Turn this into a strategy or business case?" (strategy/execution); "Define the target account profile and beachhead?" (go-to-market); "Develop positioning against these competitors?" (marketing).

## Notes
- Cite sources for market data; label estimates vs data; refresh competitor intel periodically — it shifts fast.
- This is head-to-head competitor and market intel — industry-structure forces (Porter's) and macro factors (PESTLE) live in `pm-strategy`.
- References only `pm-market-research` skills.
