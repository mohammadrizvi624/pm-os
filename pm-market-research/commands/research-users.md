---
description: Comprehensive user research from data — build personas, segment users, and map the customer journey.
argument-hint: "[personas|segment|journey|all] <research data or product>"
---

# /research-users — user research synthesis

Turns raw research data into personas, behavioral segments, and a journey map. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/research-users all [upload survey results / interview notes / feedback]
/research-users personas [paste support-ticket data]
/research-users journey our onboarding
/research-users            # asks what you have and what to build
```

## Modes
Parse `$ARGUMENTS` for the mode and inputs.
- `personas` → **user-personas**
- `segment` → **user-segmentation** (behavioral clusters from your user data — not market-level; that's `/market segments`)
- `journey` → **customer-journey-map** (built for the primary persona)
- `all` (default) → personas → segment → journey, in that order (journey uses a persona from step 1).

## Workflow
1. Confirm the inputs (survey/interviews/tickets/analytics, or a product description for exploratory work), what you want to understand, and what decision it informs. Read attached files first; be explicit about confidence when data is thin (5 interviews → hypotheses, not conclusions).
2. Run the mode's skill(s). In `all`, map segments back to personas where they overlap.

## Output (`all`)
Save to `./outputs/<YYYY-MM-DD>_user-research_<slug>.md`:
```
## User research report: <product>   (Date · data sources · sample size)
Executive summary — 3-5 sentences: key findings + implications
Personas — per persona: who · primary JTBD · top pains · top gains · behavioral pattern · prevalence (% if data allows) · one unexpected insight
User segments — | Segment | Size | Primary JTBD | Product fit | Value | Growth |
Customer journey — | Stage | Touchpoints | Emotion | Pain points | Opportunities |  + biggest drop-offs and moments of delight
Key insights (evidence-backed) · Recommendations · Open questions (what the data didn't answer)
```

## Next steps
In-plugin/generic: "Read sentiment across these segments?" → `/analyze-feedback`; "Size the segments as a market?" → `/market`. Going deeper on a persona with interviews happens in discovery.

## Notes
- Behavioral segments beat demographic ones for product decisions.
- Every persona should influence a decision — no decorative personas.
- If no data is provided, generate research-informed hypotheses and say how to validate them.
- References only `pm-market-research` skills.
