---
name: synthesize-research
description: "Synthesize findings ACROSS multiple interviews or research sources into themes and insights. Use after several interviews/summaries exist, to find patterns, write insight statements, and surface opportunities. The cross-study 'so what' step beyond single-transcript summaries."
---
# Synthesize research (across sources)

Aggregates many summaries/sources into patterns, evidence-weighted insight statements, and implications that feed the OST and roadmap.

## Inputs
- The set of interview summaries and/or survey/feedback data to synthesize (from `./outputs/` or supplied).

## Load company context
Read `./company-context/03-users-personas.md` and `05-metrics-goals.md`.

## Method
1. Affinity-map: cluster observations and quotes across sources into themes. Let themes emerge from the data, not from prior assumptions.
2. For each theme, write an insight statement: a clear claim about behavior/need, the evidence (how many sources, which personas), and a confidence level.
3. Note disconfirming evidence and where sources disagree — don't smooth it over.
4. Translate insights into implications: opportunities (route to `opportunity-solution-tree`), validated/invalidated assumptions, next steps.
5. Separate well-evidenced findings from hunches needing more data.

## Output
Save to `./outputs/<YYYY-MM-DD>_research-synthesis_<slug>.md`. Template:
```
Sources: <N interviews, survey, …>
Theme: <name>
  Insight: <claim about user behavior/need>
  Evidence: <N sources / which personas>   |   Confidence: high/med/low
  Conflicts: <disconfirming evidence>
  Implication: <opportunity → OST | assumption confirmed/invalidated | next step>
```

## Avoid
- Cherry-picking quotes to fit a pre-formed conclusion.
- Presenting low-confidence patterns as established findings.
