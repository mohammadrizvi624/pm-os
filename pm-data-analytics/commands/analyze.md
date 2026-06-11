---
description: Work with product data — pull it (SQL), then analyze funnels, cohorts, or diagnose a metric move.
argument-hint: "[funnel|cohort|investigate|query] <question or data>"
---

# /analyze — work with the data

Routes to the right data activity. `query` pulls the data; the others analyze it. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/analyze funnel onboarding drop-off
/analyze cohort retention by signup month [upload CSV]
/analyze investigate activation dropped 8% last week
/analyze query DAU by plan tier, last 30 days
/analyze            # asks what you're digging into
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `query` → **sql-query** (natural language → SQL; usually the first step to get the data)
- `funnel` → **funnel-analysis**
- `cohort` → **cohort-analysis**
- `investigate` → **metric-investigation** (root-cause a metric move; pulls funnel/cohort cuts as needed)

If the user has no data yet, start with `query` to pull it, then chain into the chosen analysis.

## Output notes (per mode)
- `cohort`: retention table (cohort × period), best/worst cohort + trend, benchmark vs target, follow-up queries. Push for a meaningful retention event (a core action, not "logged in"); flag founding-user bias and seasonal effects.
- `investigate`: rule out an instrumentation change first, then decompose and localize before naming a cause with a confidence level.

## Next steps
In-plugin: "Test a fix?" → `/experiment`; "Monitor it ongoing?" → `/measure dashboard`. Going deeper on the *why* with users is qualitative — that's discovery/market-research.

## Notes
- References only `pm-data-analytics` skills.
