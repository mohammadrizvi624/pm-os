---
name: product-strategy
description: "Create a comprehensive product strategy using the 9-section Product Strategy Canvas — vision, segments, costs, value propositions, trade-offs, metrics, growth, capabilities, defensibility. Use when building a product strategy, writing a strategic plan, or defining product direction (where to play, how to win)."
---
# Product strategy

Produces a complete strategy on the 9-section Product Strategy Canvas, disciplined by Rumelt's strategy kernel: a clear **diagnosis** of the situation, a **guiding policy** (where to play / how to win), and **coherent actions** that reinforce each other. The canvas is the artifact; the kernel keeps it from being a wish-list.

## Inputs
- The product and the strategic question (e.g. "strategy for the next year," "entering segment X"). Read attached market/customer/competitor material first.

## Load company context
Read `./company-context/00-company.md`, `01-product.md`, `03-users-personas.md`, `04-market-competitors.md`, `05-metrics-goals.md`.

## Method — the 9 sections
1. Vision — what we aspire to (pull from `product-vision` if it exists).
2. Market segments — defined by problems/JTBD, not demographics; which segment first and why.
3. Relative costs — do we win on low cost or on unique value? Our cost position vs competitors.
4. Value proposition — per target segment: what before → how → what after → alternatives.
5. Trade-offs — what we will NOT do; how saying "no" creates focus.
6. Key metrics — the North Star and the one metric that matters this quarter (OMTM).
7. Growth — sales-led vs product-led; primary channels; unit economics.
8. Capabilities — competencies/resources needed; build vs partner.
9. Can't/Won't (defensibility) — why competitors can't easily copy this (network effects, switching costs, IP).
Then validate coherence (do the nine reinforce each other?), surface the hypotheses that must be true, and suggest cheap tests for the riskiest.

## Output
Save to `./outputs/<YYYY-MM-DD>_product-strategy_<slug>.md` as the 9 sections above, ending with: Coherence check · Critical hypotheses · Tests to run.

## Avoid
- A canvas where sections don't reinforce each other (a list, not a strategy).
- Skipping trade-offs — "what we won't do" is where strategy lives.
- Treating it as one-and-done; revisit as the market shifts.
