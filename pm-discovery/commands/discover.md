---
description: Run a full product discovery cycle — from framing through assumption mapping to experiment design.
argument-hint: "<problem or idea> [new|existing]"
---

# /discover — full discovery cycle

Chains this plugin's discovery skills into one end-to-end workflow, pausing at checkpoints so you can steer. Each underlying skill loads `./company-context/*` and saves its artifact to `./outputs/`. Expect a 15-30 min guided session.

## Invocation
```
/discover Smart notifications for our PM tool
/discover new: AI writing assistant for non-native speakers
/discover                 # asks what you're discovering
```

## Workflow

### 0 · Set the stage
Determine `new` vs `existing` from the argument; else infer from `company-context/01-product.md`; else ask. State which you're using.

### 1 · Frame the problem
Apply **frame-problem**.
▸ Checkpoint: confirm the problem statement and success signal before continuing.

### 2 · Map the opportunity space
Apply **opportunity-solution-tree**, sourcing opportunities from any research in `./outputs/`.
▸ Checkpoint: pick the target opportunity (top 2-3).

### 3 · Ideate (divergent)
Apply **brainstorm-new-product** (new) or **brainstorm-features** (existing) against the target opportunity.
▸ Checkpoint: "Here are the ideas — pick 3-5 to carry forward, or carry all."

### 4 · Shortlist (converge)
Apply **prioritize-ideas** to the carried-forward set.
▸ Checkpoint: confirm the validate-next shortlist.

### 5 · Surface assumptions
For each shortlisted idea, apply **identify-assumptions**. Compile one master list.

### 6 · Prioritize assumptions
Apply **prioritize-assumptions** (Impact × Uncertainty).
▸ Checkpoint: confirm the leap-of-faith set to test first.

### 7 · Design experiments
Apply **brainstorm-experiments** for the leap-of-faith assumptions.

### 8 · Compile the discovery plan
Stitch the artifacts into one plan, saved to `./outputs/<YYYY-MM-DD>_discovery-plan_<slug>.md`:
```
## Discovery plan: <topic>
Date: <today> · Stage: <new|existing> · Discovery question: <…>

Outcome & target opportunity: <from the OST>
Ideas carried forward: <shortlist + rationale>
Critical assumptions:
| # | Assumption | Category | Impact | Uncertainty | Priority |
Validation experiments:
| # | Tests assumption | Method | Metric & threshold | Effort |
Sequence: Week 1 … / Week 2 … / Week 3 analysis & decision
Decision framework:
- If <experiment> passes → <next step>
- If it fails → <pivot / kill / dig deeper>
```

### 9 · Next steps (within discovery)
Offer in-plugin follow-ups only: run an experiment and bring results back via `/interview summarize` or `/interview synthesize`; or `/validate` a different idea. Hand-off to execution or GTM happens in those plugins once discovery validates.

## Notes
- Pause at every checkpoint; the user can redirect, skip, or go deeper.
- New product → weight desirability first; existing → check usage data to inform assumptions.
- This command references only `pm-discovery` skills.
