---
name: feature-request-triage
description: "Theme and prioritize a batch of inbound feature requests by opportunity, strategic alignment, impact, effort, and risk. Use when triaging customer/stakeholder requests, processing a request backlog, or turning raw asks into prioritized opportunities."
---
# Feature-request triage

Turns a pile of raw feature requests into themed opportunities ranked by value — prioritizing the *problems* behind requests, not the requested features themselves.

## Inputs
- The list of feature requests (spreadsheet/CSV, support export, or pasted). Read attached files first.

## Load company context
Read `./company-context/00-company.md` (strategy/theme), `03-users-personas.md`, `05-metrics-goals.md` (what outcomes matter now).

## Method
1. Confirm the product objective and the outcomes that should guide prioritization.
2. Cluster the raw requests into themes; name each theme by the underlying customer problem (not the requested feature).
3. Score the themes. For customer problems, use Opportunity Score = Importance × (1 − Satisfaction) (Olsen; from `pm-core`'s `pm-frameworks`); also weigh strategic alignment, rough impact, effort, and risk.
4. Surface the top 3 themes; for each give rationale (customer need + alignment), alternative solutions worth considering, the riskiest assumptions, and how to test them cheaply.

## Output
Save to `./outputs/<YYYY-MM-DD>_request-triage_<slug>.md`:
```
Themes: | Theme (problem) | # requests | Opportunity score | Strategic fit | Impact | Effort | Risk |
Top 3:
- <theme> — rationale — alternative solutions — risky assumptions → how to test
```

## Avoid
- Letting customers design the solution — prioritize the problem, not the literal feature asked for.
- Treating request volume as importance; weight by opportunity (importance × dissatisfaction), not count alone.
