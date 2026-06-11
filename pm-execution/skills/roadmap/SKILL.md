---
name: roadmap
description: "Build or refine an outcome-focused product roadmap — initiatives expressed as customer/business outcomes with flexible time windows, not a dated feature list. Use when creating a roadmap, making one more strategic, or transforming an output/feature roadmap into outcomes."
---
# Roadmap

Produces a roadmap organized around outcomes (what changes for customers and the business) rather than a feature checklist — more resilient to change and clearer on intent.

## Inputs
- An existing roadmap to refine/transform, or the strategy + OKRs to build one fresh. Read attached files first.

## Load company context
Read `./company-context/00-company.md` (strategy), `02-product-team.md` (team goals), and `05-metrics-goals.md` (the outcomes/metrics roadmap items should ladder up to).

## Method
1. If given an output/feature roadmap, transform it: for each initiative ask "so what?" until you reach the real customer/business value.
2. Rewrite each initiative as an outcome statement: **Enable [segment] to [customer outcome] so that [business impact]** — with the metric that signals success.
3. Organize by horizon — now / next / later (or themed quarters) — using flexible windows, not exact dates. Multiple outputs may serve one outcome; keep the focus on the outcome.
4. Add strategic context: how the outcomes align to strategy, key assumptions, and sequencing/dependencies. Tailor to audience — exec roadmaps stay outcome-only; engineering roadmaps can list initiatives under each outcome. Keep `Later` items less specific (outcomes without committed solutions).

## Output
Save to `./outputs/<YYYY-MM-DD>_roadmap_<slug>.md`:
```
## Roadmap: <product>
| Horizon | Outcome (Enable … to … so that …) | Success metric | Candidate initiatives | Assumptions |
(now / next / later, or themed quarters)
Strategic context: how these ladder up to strategy + key dependencies
If transforming an existing roadmap: a notes table — | Original feature | Transformed outcome | Why this framing |
```

## Avoid
- Feature lists with hard dates (false precision) — outcomes with flexible windows instead.
- Outcomes that aren't measurable or testable.
