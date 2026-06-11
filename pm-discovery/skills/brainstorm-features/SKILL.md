---
name: brainstorm-features
description: "Brainstorm features or improvements for an EXISTING product. Use when ideating within a live product — addressing known pains, OST opportunities, user feedback, or improving a flow. Ideas are bounded by the current product, users, and constraints. For 0-to-1 ideation, use brainstorm-new-product instead."
---
# Brainstorm — features / improvements (existing product)

Ideation bounded by a real product: its users, surfaces, architecture, and constraints. This is *continuous* discovery — iterating on a live product, not deciding whether one should exist (that's `brainstorm-new-product` / initial discovery).

## Inputs
- The target opportunity, pain, or OST branch to ideate against. If research, an OST, or personas are attached, read them first; if a product/competitor URL is given, you may research it.

## Load company context
Read `./company-context/01-product.md` (surfaces, architecture, limitations), `03-users-personas.md`, `04-market-competitors.md`. Pull the target opportunity and any feedback/VoC from `./outputs/`.

## Method
1. Anchor to a specific opportunity or pain — generate against it, not in the abstract.
2. Ideate as a product trio (Teresa Torres) — generate ~5 ideas from each lens: PM (business value, strategic fit, impact), Designer (UX, usability, delight), Engineer (technical possibilities, data leverage — the best ideas often come from engineers), Customer (what they'd actually want). Include "improve the existing flow" and "remove a step," not only "add a feature."
3. Respect known constraints from `01-product.md`, but flag when a constraint is the thing worth challenging.
4. For each idea: concept, opportunity served, product fit; note its biggest unknown to ease the handoff.
5. Cluster into themes; flag quick wins vs larger bets.

## Output
Save to `./outputs/<YYYY-MM-DD>_ideas-features_<slug>.md`. Template:
```
Opportunity: <target>
Theme: <grouping>
- Idea: <concept> | Serves: <opportunity/pain> | Fit/effort: <quick win | bet> | Biggest unknown: <…>
```
Ranking happens in `prioritize-ideas`.

## Avoid
- Ideas untethered from a real opportunity or persona.
- Ignoring `01-product.md` constraints — or treating every constraint as fixed.
