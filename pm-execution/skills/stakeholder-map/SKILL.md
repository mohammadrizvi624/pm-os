---
name: stakeholder-map
description: "Map stakeholders on a Power × Interest grid and produce a tailored communication plan per quadrant. Use when managing stakeholders, aligning cross-functional teams, prepping for a launch, or planning engagement for an initiative."
---
# Stakeholder map

Places stakeholders on a Power × Interest grid and turns each quadrant into a concrete communication strategy, so the right people are engaged the right amount.

## Inputs
- The initiative, plus any org charts, briefs, or team rosters. Read attached files first; otherwise infer likely stakeholders from the product context.

## Load company context
Read `./company-context/02-product-team.md` (the immediate team), `06-stakeholders.md` (wider stakeholders, roles, relationships), and `00-company.md`.

## Method
1. List all relevant stakeholders — execs, eng, design, marketing, sales, support, legal, finance, partners, end users.
2. Rate each on **Power** (ability to influence decisions/resources) and **Interest** (how much the initiative affects/engages them), High/Low.
3. Place on the grid and apply the quadrant strategy:
   - High power / High interest → **Manage closely** (involve early, regular 1:1s).
   - High power / Low interest → **Keep satisfied** (periodic updates, escalate only critical).
   - Low power / High interest → **Keep informed** (status updates, demos, gather feedback).
   - Low power / Low interest → **Monitor** (light-touch, on request).
4. For each, set communication frequency, channel, key message, and the risk if neglected; note their **stance** (supportive / neutral / resistant) to prioritize relationship-building.
5. Flag stakeholders with competing interests and suggest alignment moves; define an **escalation path** (who unblocks a stalled decision) and a **RACI** for the key decisions.

## Output
Save to `./outputs/<YYYY-MM-DD>_stakeholder-map_<slug>.md`:
```
Power × Interest grid (who sits where)
| Stakeholder | Role | Power | Interest | Stance | Strategy | Frequency | Channel | Key message |
Conflicts & alignment plan · Escalation path
RACI (key decisions): | Decision | Responsible | Accountable | Consulted | Informed |
```

## Avoid
- One-size communication — tailor frequency and message to the quadrant.
- Treating it as static — revisit as the initiative and stakeholders shift.
