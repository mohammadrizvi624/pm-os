---
description: Build the growth engine — acquisition channels/motions, product-led growth loops, and lifecycle retention.
argument-hint: "[loops|channels|lifecycle|full] <product or growth challenge>"
---

# /grow — growth engine

Routes a single growth skill, or `full` chains acquire → compound → retain. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/grow full B2B collaboration tool stalled at 5K users
/grow loops where can we build a viral/collaboration loop
/grow channels which motions fit our low-ACV self-serve product
/grow lifecycle improve activation and win-back
/grow            # asks about the growth challenge
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `channels` → **acquisition-channels** (7 GTM motions scored → motion stack + concrete ideas)
- `loops` → **growth-loops** (5 loop types → primary loop + coefficient)
- `lifecycle` → **lifecycle-marketing** (onboarding/activation/retention/win-back)
- `full` (default) → channels → loops → lifecycle (acquire → compound → retain).

## Workflow (`full`)
1. Confirm current state (users, growth rate, channels, business model, budget).
2. **acquisition-channels**: score the 7 motions, recommend a 2-4 motion stack with concrete ideas.
3. **growth-loops**: design the highest-leverage product-led loop to compound acquisition.
4. **lifecycle-marketing**: the retention/activation flows that keep the users you win.

## Output (`full`)
Save to `./outputs/<YYYY-MM-DD>_growth-strategy_<slug>.md`:
```
## Growth strategy: <product>   (current state · goal)
Motion mix: | Motion | Investment | Expected ROI | Timeline | Tools |
Growth loops: ranked fit → primary loop (mechanism · metrics · coefficient) + secondary
Lifecycle flows: stage → trigger → channel → message → metric
Growth experiments: | Experiment | Tests what | Effort | Expected learning |
Metrics: loop health · CAC by channel · payback (flag if CAC > ~1/3 LTV)
90-day plan: month 1 experiment → month 2 scale/cut → month 3 systematize
```

## Next steps
In-plugin: "Plan a launch around this?" → `/go-to-market`. Generic: the North Star + metric tree, experiment rigor (stats), and loop-health instrumentation live in `pm-data-analytics`.

## Notes
- Loops compound; one-off tactics don't — prioritize loops, and match motions to ACV/sales cycle.
- References only `pm-marketing` skills.
