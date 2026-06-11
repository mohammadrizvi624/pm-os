---
name: user-personas
description: "Create refined, research-backed user personas — JTBD, pains, gains, and an unexpected insight each. Use when building personas from survey/interview data or profiling the user base for product decisions. (Persona-level, grounded in data; for market-level segments use market-segmentation.)"
---
# User personas

Synthesizes research into a small set of distinct, actionable personas grounded in actual data — not demographic stereotypes.

## Inputs
- The research data (CSV, survey responses, interview transcripts, usage notes). Read attached files first.

## Load company context
Read `./company-context/03-users-personas.md` (existing personas to refine/extend) and `01-product.md`. Use `09-glossary.md` terms if present.

## Method
1. Read all provided research; identify recurring goals, behaviors, pains, and motivations.
2. Group similar users into ~3 distinct, non-overlapping personas by shared JTBD and motivation (behavior over demographics).
3. For each persona, synthesize a coherent profile from the data; use brief verbatim quotes as evidence.
4. Cross-check each insight against the data; flag gaps needing more research.

## Output
Save to `./outputs/<YYYY-MM-DD>_personas_<slug>.md`. Per persona (≈3):
```
Name & profile: <role / context / key characteristics>
Primary JTBD: <core outcome, context, frequency>
Top 3 pains: …
Top 3 desired gains: … (how they measure success)
Unexpected insight: <a counterintuitive pattern from the data, and why it matters>
Product fit: <how the product serves / could serve this persona>
```

## Avoid
- Demographic stereotypes with no behavioral basis.
- Inventing details not supported by the data — flag gaps instead.
