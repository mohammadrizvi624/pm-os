---
name: survey-design
description: "Design a survey to validate a signal quantitatively. Use when the user wants to test something at scale, quantify a pattern found qualitatively, size a problem, or run a survey. Produces an unbiased instrument plus a sampling and analysis plan. Complements interviews (qual) with quant."
---
# Survey design

Designs a quantitative instrument to test or size a signal across many respondents, with bias-resistant questions and a plan to analyze the result.

## Inputs
- The objective or hypothesis to quantify (from the user or a `synthesize-research` finding to validate at scale).

## Load company context
Read `./company-context/03-users-personas.md` (target respondents) and `05-metrics-goals.md` (what the result informs).

## Method
1. State the objective and the specific decision the survey informs. No decision → not ready.
2. Define target respondents and roughly how many for a usable (directional) read.
3. Draft questions by type: closed/scaled for measurement (Likert, single/multi-select), a few open-ended for color. Order easy/general → specific; sensitive items late.
4. Audit each for bias: no leading/loaded wording, no double-barreled questions, balanced scales, mutually exclusive options, neutral/"none" where needed.
5. Pre-write the analysis plan: how each question maps to the decision; what result confirms vs not.

## Output
Save to `./outputs/<YYYY-MM-DD>_survey_<slug>.md`. Template:
```
Objective + decision: <…>
Target respondents: <persona> | Rough N: <…>
Questions:
  1. <question> [type: single-select / Likert 1-5 / open] — measures: <what>
Analysis plan:
  - Q1 → <decision mapping>; confirms if <threshold>
```

## Avoid
- Leading, double-barreled, or jargon-laden questions.
- Collecting data with no pre-defined analysis or decision.
