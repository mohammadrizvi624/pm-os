---
description: Onboarding interview for a new PM — asks about your company, product, and (especially) your immediate team, then writes the company-context files.
argument-hint: "[optional: paste notes, an org chart, or a strategy doc]"
---

# /onboard — populate context by interview

Interviews you about your new role and fills in `./company-context/` from your answers — built for a newly-joined PM starting from zero. Backed by the **company-context** skill.

## Invocation
```
/onboard
/onboard [upload an org chart, strategy deck, or onboarding notes]
```

## Workflow
1. If files are provided, read them first and pre-fill what you can; only ask about the gaps.
2. Interview in this order, **leading with the immediate product team** (the context that matters most day to day):
   - **Your product team** (`02-product-team`): what does your team own? who's on it (PM, eng, design, data) and their roles? the team's mission and goals/OKRs and the metrics you're judged on? rituals and cadences? key dependencies/adjacent teams? how decisions get made?
   - **Company** (`00`): mission, business model, strategy, stage.
   - **Product** (`01`): what it is, surfaces, current state.
   - **Users** (`03`), **market/competitors** (`04`), **metrics/goals** (`05`), **wider stakeholders** (`06`), **tools** (`07`), **voice** (`08`), **glossary** (`09`).
   Ask a few focused questions at a time, not a wall; infer sensibly and confirm rather than interrogating.
3. Write each file (starting from the bundled templates) into your **project root** `./company-context/` — the live folder every plugin reads; mark anything you couldn't get as `[TODO: confirm]` so it's visible to fill later.
4. Summarize what's captured and the top gaps to chase down in the first week.

## Next steps
"Refine or gap-check later?" → `/context audit`. The filled context now powers every other plugin.

## Notes
- Keep it friendly and brisk — this is a new joiner's first week, not an interrogation.
- References only `pm-core`.
