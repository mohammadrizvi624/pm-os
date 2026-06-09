---
name: ansoff-matrix
description: "Generate an Ansoff Matrix mapping growth options across market penetration, market development, product development, and diversification. Use when weighing growth directions, planning expansion, or evaluating risk-reward across growth paths."
---
# Ansoff Matrix

Maps growth options on two axes — existing vs new product, existing vs new market — into four quadrants of increasing risk.

## Inputs
- The current product and market, growth targets/timeline, and capabilities. Read attached material first.

## Load company context
Read `./company-context/00-company.md`, `01-product.md`, `04-market-competitors.md`, `05-metrics-goals.md`.

## Method
For each quadrant, surface 2-3 specific opportunities with rough size, resources, and risk:
- Market penetration (current product, current market) — usage frequency, win competitors' customers, reduce churn, upsell. Lowest risk.
- Market development (current product, new market) — new geographies/segments/channels, localization. Medium risk.
- Product development (new product, current market) — new features, adjacent lines, bundles, premium/lite. Medium risk.
- Diversification (new product, new market) — related or unrelated; often via M&A/JV. Highest risk.
Then prioritize by strategic fit, revenue potential, feasibility, and defensibility; recommend a sequence (usually penetration first), and flag risks.

## Output
Save to `./outputs/<YYYY-MM-DD>_ansoff_<slug>.md`: the 2×2 with opportunities per quadrant (size / resources / risk), prioritized top 2-3, and a phased sequence.

## Avoid
- Spreading across all four quadrants at once — win one before expanding.
- Ignoring that risk and timeline rise sharply toward diversification.
