---
name: prd
description: "Write a Product Requirements Document — the authoritative spec for a product or feature: problem, objective & success metrics, segments, value prop, solution, and release plan. Use when writing a PRD, documenting requirements, preparing a feature spec, or reviewing an existing one."
---
# PRD (product requirements document)

Produces the authoritative spec that aligns engineering, design, and stakeholders on the what, why, and how — concise but complete, with assumptions flagged for validation.

## Inputs
- The product/feature and any context (research, designs, data, an existing PRD to review). Read attached files first; use web research for market context where it helps.

## Load company context
Read `./company-context/00-company.md` (vision/strategy to align to), `01-product.md`, `02-product-team.md` (the team & its goals), `03-users-personas.md`, `05-metrics-goals.md` (NSM/KPIs for success metrics), and `08-voice-tone.md`. Flag missing facts as `[TODO: confirm]`.

## Method
Work the 8 sections; pull objectives from strategy and success metrics from the metrics doc.
1. Summary — 2-3 sentences: what this doc is.
2. Contacts — key stakeholders (name, role).
3. Background — context, why now, what changed/became possible.
4. Objective — why it matters, benefit to customers + business, alignment to strategy; **non-goals** (explicit out-of-scope, to stop scope creep); and a **success-metrics table** (metric · current · target · how measured), in SMART OKR form (see the `okrs` skill).
5. Market segment(s) — who it's for (defined by jobs/problems, not demographics) and constraints.
6. Value proposition(s) — jobs/needs addressed, gains, pains avoided, why we beat alternatives.
7. Solution — UX/prototypes, key features tiered **P0 / P1 / P2** (must / should / nice-to-have), technology (if relevant), and assumptions (believed, not proven).
8. Release — relative timeframes (not exact dates), v1 vs later.
9. Open questions — genuinely unresolved items only (not things answerable from context), each with an owner.

## Output
Save to `./outputs/<YYYY-MM-DD>_prd_<slug>.md`. Plain language, short sentences, clear headings. Include the success-metrics table (`| Metric | Current | Target | How measured |`), the P0/P1/P2 requirements, and an open-questions table (`| Question | Owner | Needed by |`). Link each section back to strategy; flag every assumption. Offer to run `pre-mortem` on the draft.

## Avoid
- Exact ship dates — use relative windows.
- Solutioning before the problem and success metric are clear.
- Jargon and internal codenames.
