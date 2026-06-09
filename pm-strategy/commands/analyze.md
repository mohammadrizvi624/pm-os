---
description: Run strategic analysis — SWOT, PESTLE, Porter's Five Forces, Ansoff — singly, or all four in one scan.
argument-hint: "[swot|pestle|five-forces|ansoff|scan] <product, market, or industry>"
---

# /analyze — strategic analysis

Routes to a single analysis lens, or `scan` runs all four and synthesizes them into one strategic-context read. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/analyze swot our onboarding
/analyze pestle EdTech corporate-learning market
/analyze five-forces ride-hailing
/analyze ansoff our SaaS, growth planning
/analyze scan our fintech, board strategy review
/analyze            # asks which lens or scan
```

## Modes
Parse `$ARGUMENTS` for the lens and the target.
- `swot` → **swot-analysis**
- `pestle` → **pestle-analysis**
- `five-forces` → **porters-five-forces**
- `ansoff` → **ansoff-matrix**
- `scan` → all four in sequence, then synthesize.

For single-lens modes, run the skill and save its output. Ground PESTLE/Porter's in current data via web research where relevant.

## Scan mode
1. Confirm product/market and purpose (planning, market entry, investor prep, review).
2. Run `swot-analysis` → `pestle-analysis` → `porters-five-forces` → `ansoff-matrix`, each grounded in specifics.
3. Synthesize across them, then save to `./outputs/<YYYY-MM-DD>_market-scan_<slug>.md`:
```
## Strategic market scan: <market/product>   (Date · Purpose)
Executive summary — 5-7 sentences: the situation + key recommendations.
SWOT — four quadrants + actions (leverage S×O, mitigate W×T)
PESTLE — | Factor | Current state | Impact | Trend | Timeframe |
Five Forces — | Force | Intensity | Key drivers | Implications | + overall attractiveness
Ansoff — | Strategy | Opportunity | Risk | Investment | Priority |
Cross-framework synthesis — converging signals · strategic imperatives · key risks · best opportunities
Recommendations (1-3, each backed by ≥2 frameworks)
Monitoring plan — | Signal | What to watch | Source | Frequency |
```

## Next steps
In-plugin/generic: "Turn this into a strategy?" → `/strategy`; "Model the economics?" → `/business-model` or `/monetize`. Deeper competitor teardowns happen in market research.

## Notes
- Name specific regulations, forces, and opportunities — not generic observations.
- The cross-framework synthesis is the most valuable part; make the lenses talk to each other.
- References only `pm-strategy` skills.
