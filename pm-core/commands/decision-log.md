---
description: Record and maintain product decisions — add an ADR-style entry, list past decisions, or supersede an old one.
argument-hint: "[add|list|supersede] <decision or ID>"
---

# /decision-log — record & maintain decisions

Keeps a running log of *why* decisions were made. Backed by the **decision-log** skill.

## Invocation
```
/decision-log add we'll go per-seat, not usage-based, for v1
/decision-log list
/decision-log supersede DL-003   # reverse/replace an earlier decision
/decision-log            # asks what you need
```

## Modes
Parse `$ARGUMENTS` for the mode and content.
- `add` → capture a new entry (context · decision · rationale · alternatives · owner · status).
- `list` → show a dated table (ID · title · status).
- `supersede` → add a new entry that replaces a prior one; mark the old one Superseded (don't delete it).

## Workflow
1. Apply the **decision-log** skill in the chosen mode.
2. Append to `./company-context/decisions.md` (preserve history; never edit a past entry away).

## Notes
- Log decisions future-you would want the reasoning for; skip trivia.
- References only `pm-core`.
