---
name: brainstorm-experiments
description: "Design experiments to test the riskiest assumptions cheaply. Use after prioritizing assumptions, to plan validation. Adapts to stage — pretotypes/lean experiments for new products, in-product experiments for existing ones. Defines hypothesis, method, metric, and threshold per test."
---
# Brainstorm experiments

Turns prioritized leap-of-faith assumptions into the cheapest valid tests that change our confidence. Stage (from `01-product.md`) selects the playbook. Lean-experiment/pretotype credit: Alberto Savoia, *The Right It*.

## Inputs
- The prioritized (leap-of-faith) assumptions to test (from `prioritize-assumptions`). If a PRD or assumption list is attached, read it first.

## Load company context
Read `./company-context/01-product.md` (stage, surfaces), `05-metrics-goals.md` (what to measure), `07-tools-stack.md` (analytics/experimentation tooling).

## Principles (both stages)
- Measure actual behavior, not opinions — turn "would you…?" into an observed action.
- Smallest test that can fail; sequence cheapest-and-most-informative first.
- Test responsibly — never put users or the business at real risk. For production tests, state the risk mitigation (guardrail metrics, small exposure %, kill criteria).

## Existing product — in-product / low-effort validation
- Prototype usability: first-click test, task completion.
- Fake door / feature stub / painted door.
- Technical spike (for feasibility risk).
- A/B test or feature-flag rollout on production (with the risk mitigation above).
- Wizard of Oz.
- Behavioral survey (not opinion-based).

## New product (0 to 1) — lean / pretotype
1. Write an XYZ hypothesis: "At least X% of Y will do Z" — X = % of the target market, Y = the specific market, Z = the committing action.
2. Design 2-3 pretotypes: landing/smoke page, explainer video, email campaign, pre-order/waitlist, concierge (manual MVP).
3. Apply Savoia's principles:
   - Skin-in-the-Game — test willingness to commit (money, time, reputation), not mere interest. Real commitment is the only reliable signal.
   - YODA over ODP — get Your Own Data from a real test; don't lean on Others' Data (market reports, analogies). "The market for your idea does not care about the market for someone else's idea."

## Output
Save to `./outputs/<YYYY-MM-DD>_experiments_<slug>.md`. One card per top assumption:
```
Assumption: <…>
Hypothesis: If we <X>, then <Y>, because <reason>.
            (new product: "At least X% of Y will do Z")
Method: <test type>  |  Tooling: <from 07-tools-stack.md>  |  Risk mitigation (if production): <…>
Metric: <single behavioral metric>  |  Pass threshold (set in advance): <…>
Effort: <time/cost>
```

## Avoid
- Designing a big build as the "test."
- Vague success criteria — set the threshold before running.
- Leaning on others' data (ODP) instead of running your own test.
