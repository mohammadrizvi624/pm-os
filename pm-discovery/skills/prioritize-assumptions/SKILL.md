---
name: prioritize-assumptions
description: "Prioritize a list of assumptions to decide which to test first, using an Impact × Uncertainty (leap-of-faith) matrix. Use after identify-assumptions, before designing experiments. Surfaces assumptions that are both critical and unproven so testing effort de-risks the most."
---
# Prioritize assumptions

Ranks assumptions so testing targets the ones both most important and least certain — the leap-of-faith set.

## Inputs
- The assumptions list to rank (from `identify-assumptions` or supplied). If a file of assumptions/research is attached, read it first.

## Load company context
Reference `./company-context/05-metrics-goals.md` to judge impact on the outcome.

## Method
1. Rate each assumption on two axes:
   - Impact — if this is wrong, how badly does the idea fail? (To quantify, you can use Opportunity Score or ICE from `pm-core`'s `pm-frameworks`.)
   - Uncertainty — how little evidence we have today.
2. Place each in the matrix and act on the quadrant:
   - High impact · High uncertainty → leap of faith: design an experiment, test first.
   - High impact · Low uncertainty → safe to proceed/build; just monitor.
   - Low impact · High uncertainty → defer (test only if the test is cheap).
   - Low impact · Low uncertainty → ignore.
3. For each leap-of-faith assumption, name the cheapest test type to raise confidence (hand to `brainstorm-experiments`).

## Output
Save to `./outputs/<YYYY-MM-DD>_assumption-priority_<slug>.md`. Template:
```
| Assumption | Impact | Uncertainty | Quadrant | Action / suggested test |
|-----------|--------|-------------|----------|-------------------------|
| <…> | H | H | leap-of-faith | fake door |

Test-first order:
1. <assumption> — <test type>
```

## Avoid
- Ranking by impact alone — an important but already-certain assumption isn't the priority.
- Folding effort into the ranking; effort belongs to choosing the cheapest test, not to which assumption is riskiest.
- Designing the full experiment here; just name the test type.
