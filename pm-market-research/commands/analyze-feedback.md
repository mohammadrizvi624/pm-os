---
description: Analyze user feedback at scale — sentiment and satisfaction, then triage what they're asking for.
argument-hint: "[sentiment|requests|full] <feedback data: CSV, text, or file>"
---

# /analyze-feedback — feedback analysis

Processes a feedback dump into sentiment insights and a prioritized request triage. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/analyze-feedback full [upload NPS / review / ticket export]
/analyze-feedback sentiment [paste app-store reviews]
/analyze-feedback requests [upload feature-request list]
/analyze-feedback            # asks what kind of feedback
```

## Modes
Parse `$ARGUMENTS` for the mode and data.
- `sentiment` → **sentiment-analysis** (scores, themes, drivers/detractors; per segment if segments exist)
- `requests` → **feature-request-triage** (theme + prioritize asks by Opportunity Score)
- `full` (default) → sentiment first, then triage the request-shaped themes it surfaced.

## Workflow
1. Confirm the feedback type (NPS, reviews, tickets, survey), any segments to split by, and what you're looking for. Read attached files first.
2. Run the mode. For NPS, analyze Detractors (0-6) / Passives (7-8) / Promoters (9-10) separately. Reference existing segments from `/research-users` rather than re-deriving them.

## Output (`sentiment` / `full`)
Save to `./outputs/<YYYY-MM-DD>_feedback_<slug>.md`:
```
## Feedback analysis   (Date · N responses · source · period)
Overall sentiment: positive% / neutral% / negative% · avg score · trend
Top themes — | # | Theme | Mentions | Sentiment | Segments most affected |
Theme deep-dive — per top theme: what users say (brief quotes) · root cause · impact · recommendation
By segment — | Segment | Volume | Avg sentiment | Top theme | Key difference |
Actionable insights · Gaps (what this feedback can't tell you)
```
`full` then appends the request-triage table (themes ranked by Opportunity Score, top 3 with assumptions to test). If input was structured (CSV), also save an enriched CSV with per-row sentiment.

## Next steps
In-plugin/generic: "Build personas from these patterns?" → `/research-users`; "Triage the themes as requests?" → `requests` mode. Going deeper on a theme with interviews happens in discovery.

## Notes
- Sentiment scoring is approximate — flag sarcasm, mixed sentiment, non-English, and small per-segment samples.
- Look for the need behind a request, not the surface topic.
- References only `pm-market-research` skills.
