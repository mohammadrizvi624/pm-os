---
name: prioritize-ideas
description: "Prioritize early-stage ideas to decide what's worth exploring or validating next. Use after brainstorming to narrow many ideas to a shortlist. Uses exploratory criteria (desirability, strategic fit, learning value, confidence), NOT delivery criteria. For sequencing a committed build backlog, that's prioritize-features in pm-execution."
---
# Prioritize ideas (discovery-stage)

Decides what's worth exploring further. Operates on raw ideas with exploratory criteria, outputs a validate-next shortlist — distinct from delivery prioritization.

## Inputs
- The candidate ideas to rank (from `brainstorm-*` outputs or a supplied list).

## Load company context
Read `./company-context/00-company.md` (strategy for fit) and `05-metrics-goals.md` (which outcomes matter now).

## Method
1. Gather the candidate ideas.
2. Score each, kept lightweight: Desirability (evidence users want it), Strategic fit (to `00-company.md`), Learning value (how much pursuing it de-risks the bigger bet), Confidence (how sure today).
3. Plot on Desirability × Confidence to separate validate-now / explore / park / drop.
4. Produce a shortlist with one-line rationale + the key unknown to test next (hand to `identify-assumptions`).

## Output
Save to `./outputs/<YYYY-MM-DD>_idea-shortlist_<slug>.md`. Template:
```
| Idea | Desirability | Strat fit | Learning | Confidence | Verdict |
|------|-----|-----|-----|-----|---------|
| <idea> | H/M/L | H/M/L | H/M/L | H/M/L | validate-now / explore / park / drop |

Shortlist:
- <idea> — <why> — next test: <unknown to validate>
```

## Avoid
- Using effort/RICE here — that's delivery prioritization.
- Killing low-confidence ideas; low confidence means "test," not "no."
