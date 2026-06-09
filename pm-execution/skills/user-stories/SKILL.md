---
name: user-stories
description: "Break a feature into user stories with acceptance criteria — 3 C's (Card, Conversation, Confirmation) and INVEST. Supports both the classic 'As a… I want… so that…' and the job-story 'When… I want… so I can…' formats. Use when writing stories, decomposing a feature, or defining acceptance criteria."
---
# User stories

Turns a feature into independent, testable stories sized for one sprint, each with clear acceptance criteria.

## Inputs
- The feature, plus any design links (Figma/Miro), context, and key assumptions. Read attached files first.

## Load company context
Read `./company-context/01-product.md`, `03-users-personas.md` (for roles/situations), and `08-voice-tone.md`.

## Method
1. Analyze the feature against the design and context; identify the user roles and distinct journeys.
2. Apply the 3 C's — Card (title + one-liner), Conversation (intent/detail), Confirmation (acceptance criteria) — and keep each story INVEST (Independent, Negotiable, Valuable, Estimable, Small, Testable).
3. Choose the framing per the team's preference:
   - Classic: "As a [role], I want to [action], so that [benefit]."
   - Job story (default when role is fuzzy or you want to avoid persona assumptions): "When [situation], I want to [motivation], so I can [outcome]." (JTBD — focus on the job, not the role.)
4. Write 4-6 observable, testable acceptance criteria per story, covering the happy path, edge cases, and an accessibility/performance check. Link the design. Tag each story with priority (P0/P1/P2), rough effort (S/M/L), and dependencies; flag any that need design input or a technical **spike** (investigation before it can be estimated). Give error handling and notable edge cases their own stories, not happy-path bullets.

## Output
Save to `./outputs/<YYYY-MM-DD>_stories_<feature>.md`. Per story:
```
Title: <feature/outcome>   ·   Priority P0/P1/P2 · Effort S/M/L · Dependencies: …
Story: As a … I want … so that …   (or)   When … I want … so I can …
Design: <link>
Acceptance criteria: 1…6 (clear, testable, observable)
```
End with a **story map** (must-have → should-have → nice-to-have) and any cross-cutting technical notes. Stories should be independent and individually shippable within a sprint; group into epics/phases if there are 15+.

## Avoid
- Acceptance criteria that aren't observable/testable.
- Stories too big for one sprint, or that depend on each other to deliver value.
