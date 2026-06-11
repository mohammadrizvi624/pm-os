---
name: experiment-analysis
description: "Analyze A/B test results with statistical rigor — validate the setup, compute significance and confidence intervals, check guardrails, and give a ship / extend / stop / investigate call. Use when evaluating experiment results, checking if a test reached significance, or deciding whether to ship a variant."
---
# Experiment analysis

Turns raw A/B results into a defensible decision — checking the test was valid before trusting the lift, and weighing guardrails before declaring a win.

## Inputs
- The experiment (hypothesis, variant, metrics, traffic split, duration) and its data (CSV/export). Read attached files first; generate and run a Python script for the stats if raw data is provided.

## Load company context
Read `./company-context/05-metrics-goals.md` (primary metric + guardrails) and `07-tools-stack.md`.

## Method
1. **Restate the experiment**: hypothesis, change, primary metric, guardrails, duration, split.
2. **Validate the setup** before trusting results: sample size adequate for the effect (≥80% power); ran ≥1-2 business cycles; no sample-ratio mismatch (SRM); novelty/primacy effects washed out.
3. **Compute the stats**: control vs variant rate, relative lift, p-value (two-tailed z / chi-squared), 95% CI for the difference; flag statistical (p<0.05) and practical significance.
4. **Check guardrails**: a winning primary metric with a degraded guardrail (revenue, engagement, latency) is not a clean win.
5. **Decide** using the table below; give reasoning and next steps.

| Outcome | Call |
|---|---|
| Significant lift, guardrails clean | **Ship** — roll to 100% |
| Significant lift, guardrail concern | **Investigate** the trade-off first |
| Not significant, positive trend | **Extend** — underpowered or small effect |
| Not significant, flat | **Stop** — no real difference |
| Significant negative | **Don't ship** — revert, analyze why |

## Output
Save to `./outputs/<YYYY-MM-DD>_experiment-analysis_<slug>.md`:
```
## A/B results: <test>   (hypothesis · duration · N control/variant)
Setup validation: power · SRM · duration · novelty
| Metric | Control | Variant | Lift | p-value | Sig? |  (primary + guardrails)
Recommendation: Ship/Extend/Stop/Investigate — reasoning — next steps
```

## Avoid
- Calling significance on an underpowered test or before a full business cycle.
- Declaring a win on the primary metric while a guardrail degrades.
