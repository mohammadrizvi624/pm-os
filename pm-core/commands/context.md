---
description: Stand up, update, or gap-check the company-context layer that every PM-OS skill reads.
argument-hint: "[scaffold|update|audit] [file or topic]"
---

# /context — manage the company-context layer

Routes work on `./company-context/`. Backed by the **company-context** skill.

## Invocation
```
/context scaffold            # create the 10 template files
/context update 02-product-team    # edit/fill one file
/context audit               # gap-check what's missing or stale
/context            # asks what you need
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `scaffold` → copy the bundled templates (`skills/company-context/templates/`) into your **project root** `./company-context/` if absent (don't overwrite existing). The live folder lives in your project, not in the plugin.
- `update` → open/fill a named file (or topic); ask only for the gaps, write concise, sourced facts.
- `audit` → check each file for empty/placeholder sections, stale facts, missing metrics/team goals, and company-vs-team conflicts; return a gap checklist.

## Workflow
1. Confirm which mode and (for update/audit) which files.
2. Apply the **company-context** skill; treat `02-product-team.md` as the primary operating context.
3. Write changes into `./company-context/`; report what changed and what's still `[TODO: confirm]`.

## Next steps
"Filling from scratch as a new joiner?" → `/onboard` runs the interview that populates these for you.

## Notes
- References only `pm-core`.
