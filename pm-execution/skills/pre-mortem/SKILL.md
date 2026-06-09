---
name: pre-mortem
description: "Stress-test a PRD, roadmap, or plan before reality does — attack its load-bearing assumptions, categorize risks (Tigers / Paper Tigers / Elephants), and return the cheapest test and kill criterion for each, triaged launch-blocking / fast-follow / track. Use when pressure-testing a plan or prepping for launch or exec review."
---
# Pre-mortem

A fair, sharp adversarial review that finds how a plan would fail while there's still time to test the cheapest assumption — improving the decision, not just lengthening a risk list. (Combines a pre-mortem's failure imagination with a red-team's assumption attack.)

## Inputs
- The PRD, roadmap, or plan to test. Read it thoroughly first; use web research on market/competitive conditions where relevant.

## Load company context
Read `./company-context/04-market-competitors.md` and `05-metrics-goals.md` to ground market and target risks.

## Method
1. **Extract load-bearing claims.** List what the plan asserts (about users, market, constraint, mechanism, timeline). Separate load-bearing claims (if false, the plan dies) from cosmetic ones — only attack the former.
2. **Steelman, then attack.** State the strongest version of each load-bearing claim, then attack *that* (no strawmen). Write each failure as "Fails if ___" — concrete and falsifiable.
3. **Imagine the failure.** Assume it launched and flopped; surface what was missed or over-trusted. Categorize each surfaced risk:
   - **Tiger** — a real problem you see; needs action.
   - **Paper Tiger** — others worry, but it's overblown; document to align.
   - **Elephant** — an unspoken assumption nobody's validating; investigate.
4. **Rank** the real risks by impact-if-wrong × likelihood-wrong × cheapness-to-test; the top is what to test *this week*.
5. For each surviving kill-assumption / Tiger, give: **Fails if**, **evidence to get this week**, **kill criterion** (threshold to stop/change), **cheapest test**, and a launch triage — **launch-blocking / fast-follow / track** (with owner + date for blockers).
6. State plainly what's **well-reasoned** (don't manufacture doubt) and what you **couldn't assess**.

## Output
Save to `./outputs/<YYYY-MM-DD>_pre-mortem_<slug>.md`:
```
## Pre-mortem: <plan in one line>
Top kill-assumptions (3-5, ranked): claim · fails if · evidence this week · kill criterion · cheapest test · [launch-blocking|fast-follow|track]
Tigers / Paper Tigers / Elephants
Action plan for launch-blockers: risk · mitigation · owner · due date
Go/No-Go checklist: [ ] launch-blockers mitigated · [ ] fast-follow plan assigned · [ ] monitoring for track risks · [ ] rollback plan defined · [ ] support briefed
Well-reasoned: … | Couldn't assess: …
```

## Avoid
- Strawmanning (attack the steelman or don't attack), generic risk lists, and manufactured doubt — if it's sound, say so.
- Ending on fear — end on what to *do* (the cheapest test).
