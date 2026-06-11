---
description: Brainstorm product ideas or experiments from PM, Designer, and Engineer perspectives — for an existing or new product.
argument-hint: "[ideas|experiments] [new|existing] <description>"
---

# /brainstorm — multi-perspective ideation

Routes to the right ideation skill based on two dimensions, then helps you converge. Underlying skills load `./company-context/*`.

## Invocation
```
/brainstorm ideas existing Mobile banking engagement
/brainstorm ideas new AI meal planning for busy parents
/brainstorm experiments existing Onboarding redesign
/brainstorm                 # interactive — asks what you need
```

## Workflow

### 1 · Determine mode
Parse two dimensions: what (`ideas` | `experiments`) and stage (`new` | `existing`). If a dimension is missing, ask; infer stage from `company-context/01-product.md` when possible.

### 2 · Generate
- `ideas` + `new` → apply **brainstorm-new-product**
- `ideas` + `existing` → apply **brainstorm-features**
- `experiments` → apply **brainstorm-experiments** (it adapts new vs existing internally)

### 3 · Converge & chain (offer, don't force)
After presenting the divergent set, offer in-plugin next moves:
- "Rank these into a validate-next shortlist?" → **prioritize-ideas**
- "Stress-test the top ideas?" → **identify-assumptions**
- "Design experiments for them?" → **brainstorm-experiments**

## Output
Defer to each skill's own template for the body. Present ideas grouped by perspective (PM / Designer / Engineer / Customer) with a top-5 shortlist; present experiments as cards. Save substantial output to `./outputs/`.

## Notes
- Breadth before depth — generate widely, then evaluate.
- If a research doc or transcript is attached, extract insights before ideating.
- Idea-stage ranking uses **prioritize-ideas** (exploratory criteria) — delivery prioritization (RICE/ICE on a committed backlog) lives in another plugin, not here.
- References only `pm-discovery` skills.
