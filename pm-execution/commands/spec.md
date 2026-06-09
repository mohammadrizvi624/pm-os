---
description: Define and de-risk what to build — PRD, assumption stress-test, then user stories.
argument-hint: "[prd|stories|premortem|full] <feature or problem>"
---

# /spec — define what to build

Routes a single skill, or `full` writes the PRD, stress-tests it, and breaks it into stories. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/spec full in-app notifications
/spec prd self-serve onboarding
/spec stories [upload the PRD]
/spec premortem [upload a PRD or roadmap]
/spec            # asks what you're specifying
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `prd` → **prd**
- `stories` → **user-stories**
- `premortem` → **pre-mortem** (attack the plan's load-bearing assumptions)
- `full` (default) → prd → pre-mortem the draft → break into user stories.

## Workflow (`full`)
1. Write the **prd** (problem → objective & metrics → solution → release).
2. Run **pre-mortem** on the draft *now*, while it's cheap to change. Act on launch-blocking/kill assumptions before decomposing. ▸ Checkpoint: revise the PRD if the stress-test surfaces a load-bearing failure.
3. Break the validated scope into **user-stories** with acceptance criteria.

## Next steps
In-plugin: "Slot this into the roadmap and priorities?" → `/plan`; "Ready to ship?" → `/launch`.

## Notes
- `pre-mortem` sits here (not at launch) on purpose — assumptions are cheapest to test before the work is committed.
- References only `pm-execution` skills.
