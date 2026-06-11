---
name: experiment-design
description: "Design a rigorous A/B test before you run it — hypothesis, primary and guardrail metrics, minimum detectable effect, sample size/power, duration, randomization unit, and pre-registered ship/stop criteria. Use when planning an experiment on the live product. (Pre-build cheap validation tests live in pm-discovery's brainstorm-experiments.)"
---
# Experiment design

Sets up an A/B test so its result will be trustworthy and decisive — the design half that pairs with `experiment-analysis`.

## Inputs
- The change to test and the metric it should move. Read attached files first; use baseline rates from the metrics docs to size the test.

## Load company context
Read `./company-context/05-metrics-goals.md` (baseline rates, the metric to move, guardrails) and `07-tools-stack.md` (experimentation platform).

## Method
1. Write a falsifiable **hypothesis**: if we change X, primary metric Y will move by ~Z, because [mechanism].
2. Define the **primary metric** (one) and **guardrails** (must-not-degrade: revenue, latency, churn, satisfaction).
3. Set the **minimum detectable effect** worth shipping, then compute **sample size / power** — n ≈ (Z_α/2² × 2 × p(1−p)) / MDE² per arm; target ≥80% power. State the resulting **duration** (≥1-2 full business cycles) given traffic.
4. Choose the **randomization unit** (user/account/session) and traffic split; note how you'll detect a sample-ratio mismatch.
5. **Pre-register decision criteria**: what result ships, stops, or extends — before launch, to avoid peeking bias.

## Output
Save to `./outputs/<YYYY-MM-DD>_experiment-design_<slug>.md`:
```
Hypothesis: if X then Y by ~Z because …
Primary metric · guardrails
MDE · sample size/arm · power · duration (with traffic assumption)
Randomization unit · split · SRM check
Pre-registered decision: ship if … · stop if … · extend if …
```

## Avoid
- Launching without a sample-size/duration calc (underpowered tests waste cycles).
- More than one primary metric, or deciding the success bar after seeing data.
