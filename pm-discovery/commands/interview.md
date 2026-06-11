---
description: Prepare a customer interview script, summarize a transcript, or synthesize insights across many interviews.
argument-hint: "[prep|summarize|synthesize] <topic, transcript, or summaries>"
---

# /interview — interview lifecycle

Three modes spanning the lifecycle of customer interviews. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/interview prep Onboarding for enterprise users
/interview summarize        # paste transcript or attach a file
/interview synthesize       # across your interview summaries
/interview                  # asks which mode
```

## Modes

### prep → interview-script
Ask the research goal, who you're interviewing, time available, and the decision it informs. Then apply **interview-script** (Mom Test principles, timed sections, and the note-taking template). Save the script.

### summarize → summarize-interview
Accept a transcript — pasted or attached file (read attached files first); rough notes are fine, just note the limits. Apply **summarize-interview** to produce one structured, comparable summary (current solution, jobs by importance/satisfaction, key insights, action items, theme tags).

### synthesize → synthesize-research
Gather the interview summaries in `./outputs/` (or attached). If any raw transcripts aren't summarized yet, run **summarize-interview** on them first, then apply **synthesize-research** to produce cross-study themes, insight statements (with evidence + confidence), and implications that feed the OST.

## Notes
- Behavioral > stated — weight what people *did* over what they *say* they'd do; flag contradictions within an interview.
- If a transcript surfaces competitor mentions, capture the signal (deeper competitive work lives in another plugin).
- After `synthesize`, the natural next move is `/discover` or `/validate` on the strongest opportunity.
- References only `pm-discovery` skills.
