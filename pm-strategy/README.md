# pm-strategy

Product strategy skills for the PM OS — the "where to play / how to win" thinking, distinct from articulating it (messaging → `pm-marketing`) or executing it (roadmaps/OKRs → `pm-execution`).

## Company-context contract
Every skill reads company facts from `./company-context/*` in the host project and never hardcodes them. Swap that folder to reuse the plugin at a different company. Missing context is flagged `[TODO: confirm]` rather than invented. Deliverables save to `./outputs/`.

## Skills
| Skill | Does |
|---|---|
| `product-vision` | An inspiring, achievable, emotional vision statement |
| `product-strategy` | The 9-section Product Strategy Canvas, disciplined by Rumelt's kernel |
| `business-model-canvas` | Osterwalder's 9-block BMC (established/whole-business view) |
| `lean-canvas` | Maurya's Lean Canvas (new venture / hypothesis) |
| `value-proposition` | 6-part JTBD value prop → usable value-prop statement |
| `swot-analysis` | SWOT + cross-strategies (build/defend/pivot/exit) |
| `pestle-analysis` | Macro-environment scan, rated by impact × probability |
| `porters-five-forces` | Industry-structure analysis & attractiveness |
| `ansoff-matrix` | Growth-direction options across product × market |
| `monetization-strategy` | 3-5 revenue-model options with fit, economics, validation |
| `pricing-strategy` | Pricing model, tiers, WTP/elasticity, experiments |

## Boundaries (what lives elsewhere)
- Positioning, messaging, naming, North Star → `pm-marketing`
- Competitor teardowns & segmentation → `pm-market-research` (here: only Porter's structural lens and PESTLE)
- OKRs & roadmaps → `pm-execution`
- GTM motion, ICP, launch → `pm-marketing`
- Cross-cutting prioritization (RICE/ICE/Opportunity Score) → `pm-core` `pm-frameworks`

## Commands
Workflow commands that orchestrate the skills (methodology stays in the skills; commands route modes, sequence chains, set checkpoints, and compile the consolidated deliverable).

| Command | Args | Orchestrates |
|---|---|---|
| `/strategy` | `<product or scope> [new\|existing]` | `product-vision` → `value-proposition` → `product-strategy` canvas, with checkpoints |
| `/analyze` | `[swot\|pestle\|five-forces\|ansoff\|scan]` | A single lens, or `scan` runs all four into one strategic-context report |
| `/business-model` | `[bmc\|lean]` | Routes between Business Model Canvas (established) and Lean Canvas (new) |
| `/monetize` | `[model\|pricing\|full]` | `monetization-strategy`, `pricing-strategy`, or the chain (default `full`) |

Skills with no command — `product-vision` and `value-proposition` — are steps inside `/strategy` and otherwise auto-trigger when asked (a standalone command would be a 1:1 wrapper).

> Note: `plugin.json` uses standard Claude Code plugin fields; confirm against the current plugin spec when you install.

## Author
Created by **Mohammad Hasan Rizvi**, co-authored by **Claude** (Anthropic).
