---
name: decision-log
description: "Maintain a lightweight ADR-style product decision log — context, decision, rationale, alternatives, and status, with the ability to supersede past entries. Use when recording a product/strategy/technical decision, reviewing past decisions, or reversing one."
---
# Decision log

Captures *why* decisions were made so the team isn't relitigating them later — a running, append-only log with supersede semantics (decisions evolve, they don't get silently deleted).

## Load company context
Read `./company-context/02-product-team.md` (decision-making norms, who decides) and `00-company.md`.

## Method
1. For a new decision, record an entry:
   - **ID & date**, short **title**.
   - **Context** — the situation and forces (what made this a decision).
   - **Decision** — what was decided, stated plainly.
   - **Rationale** — why; the deciding factor.
   - **Alternatives considered** — and why not.
   - **Owner / deciders** and **status** (Proposed / Accepted / Superseded).
2. To reverse a decision, add a *new* entry that **supersedes** the old one (link by ID); mark the old one Superseded rather than editing it away — the history is the point.
3. Keep entries short (a screenful); the log is a reference, not an essay.

## Output
Append to `./company-context/decisions.md` (or `./outputs/decision-log.md` if the user prefers it outside context). Entry format:
```
## [DL-007] 2026-06-08 · <title>   (Accepted)
Context: …  Decision: …  Rationale: …  Alternatives: …  Owner: …  [Supersedes DL-003]
```
For `list`, show a dated table (ID · title · status). 

## Avoid
- Editing or deleting a past decision — supersede it so the reasoning trail survives.
- Logging trivia — record decisions that future-you would want the reasoning for.
