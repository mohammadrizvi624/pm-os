---
name: summarize-interview
description: "Summarize a single customer interview transcript into a structured, comparable template — current solution, jobs scored by importance and satisfaction, key insights, action items, and theme tags. Use when processing one transcript or set of notes. For patterns across MANY interviews, use synthesize-research instead."
---
# Summarize an interview (single transcript)

Turns one transcript/notes into a consistent, comparable summary — the unit `synthesize-research` later aggregates. Write in plain language anyone could follow.

## Inputs
- The interview transcript or notes — attached file (text, PDF, audio transcription) or pasted. Read attached files first. Use "-" for anything not covered.

## Load company context
Read `./company-context/03-users-personas.md` to map the participant to a persona; use `09-glossary.md` terms if present.

## Method
1. Read the full transcript before summarizing.
2. Capture the participant and their background/context.
3. Frame around jobs: their current solution, what they like (job → desired outcome, with importance + satisfaction), and problems with it (same dimensions). Recording importance + satisfaction sets up Opportunity Score later.
4. Pull key insights — unexpected findings, strong emotions, notable brief quotes.
5. List action items as Date · Owner · Action.
6. Tag with themes so `synthesize-research` can aggregate across interviews.

## Output
Save to `./outputs/<YYYY-MM-DD>_interview-summary_<participant>.md`. Use the same headings every time:
```
Date: <…>   Participant: <name / role / persona / segment>
Background: <context>
Current solution: <what they use today>
What they like: <job → desired outcome | importance H/M/L | satisfaction H/M/L>
Problems with current solution: <job → desired outcome | importance | satisfaction>
Key insights: <unexpected findings / brief quotes>
Action items: <date · owner · action>
Themes: #tag #tag
```

## Avoid
- Editorializing beyond what was said; keep inference separate and labeled.
- Pasting the whole transcript — summarize, with brief quotes as evidence.
