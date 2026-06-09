# pm-market-research

Market-research skills for the PM OS — understanding the market, customers, and competitors. Distinct from the structural/macro lenses (Porter's, PESTLE → `pm-strategy`) and from talking to users for product discovery (interviews/surveys → `pm-discovery`).

## Company-context contract
Every skill reads company facts from `./company-context/*` in the host project and never hardcodes them. Several skills also use web research for current market/competitor data. Missing context is flagged `[TODO: confirm]` rather than invented. Deliverables save to `./outputs/`.

## Skills
| Skill | Does |
|---|---|
| `user-personas` | Research-backed personas (JTBD, pains, gains, an unexpected insight) |
| `customer-journey-map` | End-to-end journey: stages, emotions, pain points, opportunities |
| `market-segmentation` | Top-down market segments (demographics/JTBD/fit) |
| `user-segmentation` | Bottom-up behavioral clusters from your user data |
| `market-sizing` | TAM/SAM/SOM, top-down + bottom-up, with assumptions |
| `competitor-analysis` | Competitor teardowns + differentiation opportunities |
| `sentiment-analysis` | Sentiment/satisfaction from feedback at scale |
| `feature-request-triage` | Theme & prioritize inbound requests by opportunity |

## Design notes
- `market-segmentation` (market-level, top-down) and `user-segmentation` (your users, bottom-up from data) are deliberately separate — different inputs and purpose.
- `sentiment-analysis` is scoped to sentiment/satisfaction; clustering belongs to `user-segmentation`, request prioritization to `feature-request-triage` (de-overlapped from Huryn's combined version).
- `feature-request-triage` references `pm-core`'s `pm-frameworks` for Opportunity Score = Importance × (1 − Satisfaction).

## Boundaries (what lives elsewhere)
- Porter's Five Forces & PESTLE → `pm-strategy`
- Interviews, surveys, primary-research synthesis → `pm-discovery`
- ICP & beachhead-segment selection → `pm-marketing`
- Positioning & messaging → `pm-marketing`

## Commands
Workflow commands over the skills (methodology stays in the skills; commands route modes, sequence chains, and compile the consolidated deliverable).

| Command | Args | Orchestrates |
|---|---|---|
| `/research-users` | `[personas\|segment\|journey\|all]` | `user-personas` / `user-segmentation` / `customer-journey-map`; `all` = personas → segment → journey |
| `/analyze-feedback` | `[sentiment\|requests\|full]` | `sentiment-analysis` / `feature-request-triage`; `full` = sentiment then request triage |
| `/market` | `[segments\|sizing\|competitors\|scan]` | `market-segmentation` / `market-sizing` / `competitor-analysis`; `scan` = all three → opportunity brief |

Note the two segmentations split across commands by nature: `/research-users segment` is *user-level* (your data, bottom-up), `/market segments` is *market-level* (top-down). We don't ship a standalone `/competitive-analysis` (it would be a 1:1 wrapper) — it's `/market competitors`.

## Author
Created by **Mohammad Hasan Rizvi**, co-authored by **Claude** (Anthropic).
