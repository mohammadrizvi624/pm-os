---
name: okrs
description: "Draft team-level OKRs aligned to company objectives — an inspirational Objective with ~3 measurable Key Results. Generates alternative sets to spark discussion. Use when setting quarterly OKRs, aligning team goals to strategy, or learning to write effective OKRs."
---
# OKRs

Drafts ambitious, measurable OKRs that ladder up to company strategy, offered as a few credible alternatives to spark the goal-setting discussion.

## Inputs
- The team/product scope and any company objectives or strategy docs. Read attached files first; use web research for benchmarks where useful.

## Load company context
Read `./company-context/00-company.md` (company objectives/strategy), `02-product-team.md` (team goals & ownership), and `05-metrics-goals.md` (NSM/KPIs the KRs should connect to).

## Method
- Objective = qualitative, inspirational, time-bound (usually quarterly) — the directional intent.
- Key Results = ~3 quantitative metrics with target values measuring progress.
- Relationship (don't treat as alternatives): KRs are metrics, some of which are KPIs; the North Star Metric is a single customer-centric KPI a KR can express expected change in; KPIs can also serve as health/guardrail metrics.
1. Read the company strategy; find the 3-5 areas the team most influences and how its work ladders up.
2. Generate **three distinct, credible OKR sets** (none obviously best). Each: one Objective + exactly 3 Key Results (with baseline, target, owner) that are measurable, outcome-focused, and ambitious (~60-70% confidence). Add a brief rationale and show how it ladders up to the company objective.
3. Quality-check each KR: measurable from data (not judgment), not gameable (add a counter-metric if it is), and a genuine stretch (if you're sure you'll hit it, it's not ambitious enough).

## Output
Save to `./outputs/<YYYY-MM-DD>_okrs_<team>_<quarter>.md`. Three sets with equal weight:
```
Objective: <inspirational, time-bound>
Key Results: | KR | Baseline | Target | Owner |   (×3)
Rationale: why this matters to company + team
```
Then add: an **alignment map** (company objective → team objective → KRs → expected impact); a **scoring guide** (0.0-0.3 miss · 0.4-0.6 short · 0.7-0.9 target zone · 1.0 = nailed it or wasn't ambitious enough); and a **check-in cadence** (weekly traffic-light · mid-quarter review · end-quarter score).

## Avoid
- Output metrics ("launch 5 features") — measure outcomes.
- More than ~3 KRs per objective, or KRs that aren't independently measurable; flag data-availability assumptions.
