---
name: customer-journey-map
description: "Map the end-to-end customer journey — stages, touchpoints, emotions, pain points, and opportunities. Use when visualizing the customer experience, finding friction, improving onboarding, or locating drop-off and churn triggers."
---
# Customer journey map

Maps one persona's experience from awareness through advocacy, surfacing where they feel friction and where the experience can improve.

## Inputs
- The persona and product, plus any evidence (interview transcripts, analytics, support tickets, existing maps). Read attached files first.

## Load company context
Read `./company-context/03-users-personas.md` (pick a specific persona, not a generic user) and `01-product.md` (surfaces/touchpoints). Pull research from `./outputs/` if available.

## Method
1. Choose the persona traveling the journey (with their JTBD).
2. Walk the stages (adapt to the product): awareness → consideration → acquisition → onboarding → engagement → retention → advocacy.
3. For each stage, capture: touchpoints, user actions, thoughts/questions, emotion (rate it), pain points, opportunities.
4. Mark the critical moments: the aha moment (first core value), moments of truth (commit/abandon), and churn triggers.
5. Prioritize improvements by impact on conversion/retention (quick wins vs bigger bets).

## Output
Save to `./outputs/<YYYY-MM-DD>_journey-map_<persona>.md`:
```
Persona: <who, JTBD>
| Stage | Touchpoint | User action | Emotion | Pain point | Opportunity |
Critical moments: aha = … · moments of truth = … · churn triggers = …
Prioritized improvements: <quick wins> · <bigger bets>
```
For a visual map, suggest the user rebuild it in a whiteboard tool from this analysis.

## Avoid
- A generic "user" — map a specific persona.
- Listing stages with no emotion, pain, or opportunity (the value is in those columns).
