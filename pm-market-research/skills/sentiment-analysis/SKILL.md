---
name: sentiment-analysis
description: "Analyze user feedback at scale to measure sentiment and satisfaction — scores, drivers/detractors, themes, and recommendations. Use when running sentiment analysis on reviews, surveys, or support data. (Scoped to sentiment/satisfaction; for behavioral clustering use user-segmentation.)"
---
# Sentiment analysis

Measures how users feel and how satisfied they are from feedback at scale, and turns the tenor into prioritized actions. Scoped to sentiment/satisfaction — clustering users into segments is `user-segmentation`'s job (run it first and analyze sentiment *per segment* if you want that view).

## Inputs
- The feedback data (CSV, survey responses, reviews, social listening, support tickets). Read attached files first.

## Load company context
Read `./company-context/03-users-personas.md` (to map feedback to known personas/segments where possible).

## Method
1. Inventory the feedback sources.
2. Extract recurring themes — both positive and negative.
3. Score sentiment (−1 to +1) overall and, where segments exist, per segment; add an NPS proxy if the data supports it.
4. Identify satisfaction drivers (what they love) and detractors (top complaints, unmet needs, friction), with brief quotes.
5. Assess product-fit/churn signal and prioritize 2-3 highest-impact improvements by frequency × severity × business impact.

## Output
Save to `./outputs/<YYYY-MM-DD>_sentiment_<slug>.md`:
```
Sentiment score: <−1..+1>  (overall, and per segment if available)  | NPS proxy: …
Top positive themes: … (with brief quotes)
Top pain points / detractors: … (frequency · severity)
Churn/satisfaction signal: …
Highest-impact recommendations: <2-3, quick wins vs strategic>
```

## Avoid
- Re-deriving segments here — use `user-segmentation` for that; reference its segments instead.
- Conflating feature requests with sentiment — note requests but keep the focus on tenor/satisfaction (triage them in `feature-request-triage`).
- Over-reading small samples — flag low-n findings.
