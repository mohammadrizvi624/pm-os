---
name: brainstorm-new-product
description: "Brainstorm ideas for an entirely new product in early/greenfield discovery. Use when there's no existing product to constrain ideas and the space is open — a new market or 0-to-1 concept. For improvements to an existing product, use brainstorm-features instead."
---
# Brainstorm — new product (0 to 1)

Wide, divergent exploration of a greenfield space. This is *initial* discovery — testing whether the product should exist (vision, business model, market) — as opposed to continuous discovery on a live product (`brainstorm-features`). Aim for breadth, not polish.

## Inputs
- The problem/opportunity space or concept seed (from the user or a `frame-problem` output). If market/competitive research is attached, read it first; if a market or competitor URL is given, you may research it.

## Load company context
Read `./company-context/00-company.md` (mission, strategy, theme) and `04-market-competitors.md`. There's intentionally little `01-product.md` to lean on — that's the point.

## Method
1. Restate the problem/opportunity and the target customer.
2. Diverge as a product trio (Teresa Torres) — generate ~5 ideas from each lens: PM (value, market fit, differentiation), Designer (experience, onboarding), Engineer (what's newly possible, integrations), Customer (what they'd actually want). Add analogous-industry and "10x / constraint-removed" prompts.
3. Use "How might we…" framings to open the space, not converge early.
4. Capture every idea with a one-line concept + core value hypothesis — don't filter yet.
5. Lightly cluster into directions/themes, weighting attention toward core value delivery, speed-to-validate, and differentiation.

## Output
Save to `./outputs/<YYYY-MM-DD>_ideas-new-product_<slug>.md`. Template:
```
Theme: <direction>
- Idea: <concept, 1 line> | Serves: <customer> | Value hypothesis: <why it matters>
```
Keep it generative; ranking happens in `prioritize-ideas`.

## Avoid
- Converging or self-censoring during divergence.
- Importing constraints from products that don't exist yet.
