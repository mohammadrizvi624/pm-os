---
name: frame-problem
description: "Frame a product problem or opportunity before any solutioning. Use when starting discovery on a problem area, asking 'what problem are we solving', needing a problem statement or opportunity brief, or jumping to solutions without a defined problem. Produces a sourced, persona-anchored problem frame."
---
# Frame a problem / opportunity

The upstream artifact of discovery — everything else (OST, ideation, assumptions) hangs off it. The job is to define the problem precisely, not to solve it.

## Inputs
- The problem area, signal, or request to frame (from the user). Everything else comes from company context.

## Load company context
Read `./company-context/00-company.md` (strategy/theme), `01-product.md`, `03-users-personas.md`, `05-metrics-goals.md`. If any are empty, flag the gap and proceed with `[TODO: confirm]` rather than inventing facts.

## Method
1. Identify the affected persona using real names from `03-users-personas.md` — never a generic "the user."
2. State the job-to-be-done or pain in the persona's terms.
3. Pin the context: when/where it occurs, how often, and the impact on user and business.
4. Assemble evidence (data, requests, research); mark anything unproven `[ASSUMPTION: ...]`.
5. Establish why-now, tied to `00-company.md` priorities.
6. Rough the opportunity size (order-of-magnitude; show the logic).
7. Define the success signal — observable change tied to `05-metrics-goals.md`.

## Output
Save to `./outputs/<YYYY-MM-DD>_problem-frame_<slug>.md`. Template:
```
# Problem frame — <slug>
Purpose: <one line> · Owner/date: <…>

Statement: We've observed that <persona> struggles to <job> when <context>,
which leads to <impact>. We believe there's an opportunity to <opportunity>.
We'll know we've succeeded when <measurable signal>.

Affected persona: <from 03-users-personas.md>
Evidence: <what we know>   |   Assumptions: [ASSUMPTION: …]
Why now: <tie to 00-company.md>
Rough size: <order-of-magnitude + logic>
Success signal: <metric from 05-metrics-goals.md>
```
Example statement: "We've observed that *Operations leads* struggle to reconcile invoices when data spans three tools, which costs ~4 hrs/week each. We believe there's an opportunity to auto-match line items. We'll know we've succeeded when reconciliation time drops 50%."

## Avoid
- Embedding a solution in the problem statement.
- Vague personas or unsized "everyone" problems.
- Stating assumptions as facts — flag them.
