---
name: opportunity-solution-tree
description: "Build a Teresa Torres Opportunity Solution Tree to structure discovery — map one desired outcome to opportunities, solutions, and experiments. Use to organize discovery, connect customer needs to a business outcome, or decide what to explore next. Produces a structured tree, not a backlog."
---
# Opportunity Solution Tree (OST)

Connects one desired outcome to the opportunities (customer needs/pains) that could move it, the solutions that could address them, and the experiments that test them. The backbone of continuous discovery — it stops teams jumping to solutions by mapping the opportunity space first. Method: Teresa Torres, *Continuous Discovery Habits*.

## Inputs
- A desired outcome / business metric to improve, plus customer research (interviews, surveys, analytics, feedback); optionally existing opportunities or solution ideas to organize. Read attached research first.

## Load company context
Read `./company-context/05-metrics-goals.md` (outcome), `03-users-personas.md`, `00-company.md`. Pull research summaries from `./outputs/` so opportunities are evidence-based, not imagined.

## The four levels
1. Outcome — exactly one measurable outcome (from OKRs/strategy), e.g. "increase 7-day retention to 40%." An outcome, not an output like "ship X."
2. Opportunities — 3-7 customer needs/pains/desires from research, framed in their voice ("I struggle to…", "I wish I could…"). Group related ones. Prioritize with Opportunity Score = Importance × (1 − Satisfaction) (Olsen; see `pm-core`'s `pm-frameworks`); focus on the top 2-3.
3. Solutions — generate 3+ per prioritized opportunity, as a Product Trio (PM/Designer/Engineer). Don't commit to the first idea.
4. Experiments — fast, cheap tests for the most promising solutions (hand to `identify-assumptions` / `brainstorm-experiments`).

## Key principles
- One outcome at a time.
- Opportunities, not features — never let customers design the solution.
- Compare and contrast — ≥3 solutions per opportunity; avoid the first-idea trap.
- Discovery isn't linear — loop back and kill solutions that don't validate.
- Continuous, not periodic — update the tree as interviews, analytics, and experiments come in.

## Output
Save to `./outputs/<YYYY-MM-DD>_ost_<slug>.md`. Template:
```
Outcome: <one outcome metric>
└─ Opportunity: "I struggle to <…>"  [evidence: N sources | assumed]  · OppScore: <…>   ◀ TARGET
   ├─ Solution: <idea>
   │   └─ Experiment: <assumption → test>
   └─ Solution: <idea>
└─ Opportunity: "I wish I could <…>"  [assumed]
```
Tag each opportunity evidence-backed vs assumed; mark the targeted branch.

## Avoid
- Outcomes that are really outputs.
- Opportunities phrased as solutions.
- A single solution per opportunity — the value is comparison.
