---
description: Plan the work — set OKRs, build an outcome roadmap, and prioritize the backlog.
argument-hint: "[okrs|roadmap|prioritize|full] <product or scope>"
---

# /plan — plan the work

Routes a single planning skill, or `full` chains all three top-down (goals → outcomes → backlog order). Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/plan full our analytics product, Q3
/plan okrs growth team
/plan roadmap [upload current feature roadmap]
/plan prioritize [paste backlog]
/plan            # asks scope and which mode
```

## Modes
Parse `$ARGUMENTS` for the mode and scope.
- `okrs` → **okrs**
- `roadmap` → **roadmap**
- `prioritize` → **prioritize-features**
- `full` (default) → okrs → roadmap → prioritize-features.

## Workflow (`full`)
1. Confirm scope and time horizon.
2. Draft **okrs** (the outcomes to pursue). ▸ Checkpoint: pick the set to commit to.
3. Build the **roadmap** so its near-term outcomes ladder up to those OKRs.
4. **prioritize-features** to sequence the backlog beneath the near-term outcomes.

## Next steps
In-plugin: "Turn the top priority into a spec?" → `/spec`.

## Notes
- `prioritize-features` uses `pm-core`'s `pm-frameworks` (RICE/ICE), with inline fallback if pm-core isn't installed.
- References only `pm-execution` skills.
