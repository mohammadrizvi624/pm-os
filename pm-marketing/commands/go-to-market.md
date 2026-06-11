---
description: Take the product to market — define the ICP and beachhead, build the launch plan, and arm sales with battlecards.
argument-hint: "[icp|beachhead|plan|battlecard|full] <product or launch>"
---

# /go-to-market — launch

Routes a single launch skill, or `full` runs the launch chain (target → first segment → plan). Underlying skills load `./company-context/*` and save to `./outputs/`. (Named distinct from `pm-execution`'s `/launch`, which handles *internal* readiness.)

## Invocation
```
/go-to-market full AI proposal writer for consulting firms
/go-to-market icp [upload PMF survey data]
/go-to-market beachhead which segment first
/go-to-market plan new enterprise tier
/go-to-market battlecard our CRM vs Salesforce
/go-to-market            # asks about the launch
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `icp` → **icp**
- `beachhead` → **beachhead**
- `plan` → **gtm-strategy**
- `battlecard` → **sales-enablement**
- `full` (default) → icp → beachhead → gtm-strategy.

## Workflow (`full`)
1. **icp**: define the ideal customer (and disqualifiers).
2. **beachhead**: pick the first segment to win (the four criteria).
3. **gtm-strategy**: the launch plan — pulling the message from `/position` and the channels from `/grow channels`.

## Output (`full`)
Save to `./outputs/<YYYY-MM-DD>_gtm-plan_<slug>.md`:
```
## Go-to-market plan: <product>   (launch date · type)
Beachhead: who · why first · size
ICP: | Attribute | Definition | (size, industry, decision-maker, JTBD, current solution, qualification signal)
Positioning & messaging (from /position): statement + key messages by stakeholder
Channel strategy: | Channel | Tactic | Reach | Cost | Priority |
Launch timeline: | Phase | Timing | Actions | Owner |  (pre-launch · launch week · post-launch)
Success metrics: | Metric | 30-day | 90-day |  · risks & mitigations · expansion plan
```

## Battlecard output (`battlecard`)
```
We win when … / we lose when … / key differentiator
Positioning (theirs vs our counter) · feature & pricing comparison
Objection handling | Landmines to plant | Trap questions to expect
Win/loss patterns · conversation starters · resources
```
Use web research for current competitor data; keep it to a scannable one-pager; never trash the competitor — counter-position.

## Next steps
In-plugin: "Build post-launch growth?" → `/grow`. Generic: internal launch readiness (pre-mortem, stakeholder map, release notes) lives in `pm-execution`.

## Notes
- References only `pm-marketing` skills.
