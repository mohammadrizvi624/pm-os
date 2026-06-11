---
name: prioritize-features
description: "Prioritize and sequence a delivery backlog using RICE or ICE — for ranking features/stories you intend to build. Use when ordering a backlog, deciding what ships next, or building the case for a sequencing decision. (Delivery-stage; for exploratory idea ranking use pm-discovery's prioritize-ideas.)"
---
# Prioritize features

Ranks a delivery backlog with a transparent, defensible score and turns the ranking into a build sequence — distinct from discovery's exploratory `prioritize-ideas` (this assumes the items are committed-enough to build).

## Inputs
- The list of features/stories (with any reach, impact, effort, confidence data). Read attached files first.

## Load company context
Read `./company-context/05-metrics-goals.md` (the outcomes that should weight impact), `02-product-team.md` (team goals), and `00-company.md` (strategy fit).

## Method
1. Confirm the objective the backlog should serve (which metric/outcome).
2. Score each item. Use `pm-core`'s `pm-frameworks` for the formula:
   - RICE = (Reach × Impact × Confidence) / Effort — when you have rough quant inputs.
   - ICE = Impact × Confidence × Ease — lighter, for quick ranking.
   (If `pm-core` isn't installed, apply RICE/ICE inline with the standard scales.)
3. Rank by score; then sanity-check against strategy fit and dependencies (a high score blocked by a dependency moves down).
4. Produce the ranked list and a recommended sequence (what ships next, and why).

## Output
Save to `./outputs/<YYYY-MM-DD>_feature-priorities_<slug>.md`:
```
| Feature | Reach | Impact | Confidence | Effort | RICE/ICE | Notes |
Ranked sequence: 1… with one-line rationale each
Dependencies / sequencing caveats
```

## Avoid
- Treating the score as the decision — it informs judgment; call out where strategy or dependencies override it.
- Mixing exploratory ideas in here — those belong in discovery's `prioritize-ideas`.
