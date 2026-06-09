---
description: De-risk an idea or solution you already have — map its assumptions, prioritize them, and design experiments to test the riskiest.
argument-hint: "<idea or solution> [new|existing]"
---

# /validate — assumptions to test plan

The back half of `/discover`, for when you already have a solution and just want a focused test plan. Underlying skills load `./company-context/*`.

## Invocation
```
/validate In-app checklist to lift activation
/validate new: pre-order page for a hardware add-on
/validate                  # asks what you're validating
```

## Workflow

### 1 · Confirm the input
Restate the idea/solution and the stage (`new` | `existing`, inferred from `company-context/01-product.md` if not given).

### 2 · Surface assumptions
Apply **identify-assumptions** (4 core risks for existing; the broader 8 for new).

### 3 · Prioritize
Apply **prioritize-assumptions** (Impact × Uncertainty).
▸ Checkpoint: confirm the leap-of-faith set.

### 4 · Design experiments
Apply **brainstorm-experiments** for the leap-of-faith assumptions.

### 5 · Compile the test plan
Save to `./outputs/<YYYY-MM-DD>_test-plan_<slug>.md`:
```
## Test plan: <idea>
Stage: <new|existing>
Assumptions (prioritized):
| # | Assumption | Impact | Uncertainty | Quadrant |
Experiments:
| # | Tests assumption | Method | Metric & threshold | Effort |
Sequence & decision criteria:
- If <experiment> passes → <next>; if it fails → <pivot / kill / dig deeper>
```

## Notes
- Use this when the idea came from outside discovery — a strategy call, a stakeholder ask.
- Pause at the checkpoint before committing to experiments.
- References only `pm-discovery` skills.
