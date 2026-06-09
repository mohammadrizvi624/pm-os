---
description: Prepare to ship — pre-mortem the launch, map stakeholders to align, and draft user-facing release notes.
argument-hint: "[premortem|stakeholders|notes|full] <release or initiative>"
---

# /launch — ship readiness

Routes a single skill, or `full` runs the launch-readiness sequence: de-risk → align → announce. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/launch full v2.0 rollout
/launch premortem [upload the launch plan]
/launch stakeholders the pricing change
/launch notes [upload tickets / changelog]
/launch            # asks about the release
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `premortem` → **pre-mortem** (launch-failure risk pass on the launch plan)
- `stakeholders` → **stakeholder-map** (Power × Interest grid + comms plan)
- `notes` → **release-notes** (user-facing changelog)
- `full` (default) → pre-mortem → stakeholder-map → release-notes.

## Workflow (`full`)
1. **pre-mortem** the launch plan — surface launch-blocking Tigers and act on them. ▸ Checkpoint: clear blockers before announcing.
2. **stakeholder-map**: who to align for the rollout, and the comms plan per quadrant.
3. **release-notes**: the user-facing notes, matched to product voice.

## Next steps
Generic: the launch *campaign* and external messaging live in the GTM/marketing plugins — `release-notes` here is the delivery changelog.

## Notes
- `pre-mortem` appears in both `/spec` and `/launch` by design: in `/spec` it attacks the PRD's load-bearing assumptions early (cheapest test before you build); here it's the pre-ship risk pass on the launch plan. Same skill, different artifact and moment.
- References only `pm-execution` skills.
