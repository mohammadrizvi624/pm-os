---
name: business-model-canvas
description: "Generate a Business Model Canvas with all 9 building blocks. Use when creating or analyzing a business model, or documenting how the business creates, delivers, and captures value. Best for established businesses, corporate strategy, and investor materials."
---
# Business Model Canvas

Maps how the business creates, delivers, and captures value across nine blocks (Osterwalder / Strategyzer). Best for an established or whole-business view; for a new product, prefer `lean-canvas` (and the strategic thinking lives in `product-strategy`).

## Inputs
- The product/service, target customers, and any operations or competitive context. Read attached material first.

## Load company context
Read `./company-context/00-company.md`, `01-product.md`, `03-users-personas.md`, `04-market-competitors.md`.

## Method — the 9 blocks
Creating value: 1) Key partners, 2) Key activities, 3) Key resources.
Value: 4) Value propositions (which problems solved, quantitative + qualitative value).
Delivering value: 5) Customer relationships, 6) Channels (awareness → purchase → delivery → after-sales), 7) Customer segments.
Viability: 8) Cost structure (fixed vs variable; cost- vs value-driven), 9) Revenue streams (model, pricing mechanism, LTV).
Then: ensure the nine blocks reinforce each other, sanity-check unit economics (e.g. LTV > ~3× CAC), and surface key assumptions and risks.

## Output
Save to `./outputs/<YYYY-MM-DD>_bmc_<slug>.md` as the nine blocks above, ending with: Economic viability check · Key assumptions & risks.

## Avoid
- Filling blocks that don't connect — each should support the others.
- For early-stage products, over-investing in Partners/Resources blocks (low value at that stage — use `lean-canvas`).
