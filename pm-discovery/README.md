# pm-discovery

Product discovery skills for the PM OS. Twelve skills that run as a pipeline from framing a problem to synthesizing research into insights.

## The pipeline
`frame-problem` → `opportunity-solution-tree` → `brainstorm-new-product` | `brainstorm-features` → `prioritize-ideas` → `identify-assumptions` → `prioritize-assumptions` → `brainstorm-experiments` → `interview-script` → `survey-design` → `summarize-interview` → `synthesize-research`

The two `brainstorm-*` skills are alternatives at the same stage: use `brainstorm-new-product` for 0-to-1 concepts, `brainstorm-features` for improvements to an existing product.

## Company-context contract
Every skill reads company facts from `./company-context/*` in the host project and never hardcodes them. Swap that folder to use these skills at a different company — the plugin doesn't change. Missing context is flagged as `[TODO: confirm]` rather than invented.

## Outputs
Each skill saves a dated, sourced deliverable to `./outputs/` in the host project.

## Skills
| Skill | Does |
|---|---|
| `frame-problem` | Define the problem/opportunity before solutioning |
| `opportunity-solution-tree` | Map outcome → opportunities → solutions → experiments |
| `brainstorm-new-product` | Greenfield ideation for a new product |
| `brainstorm-features` | Bounded ideation for an existing product |
| `prioritize-ideas` | Narrow ideas to a validate-next shortlist (exploratory criteria) |
| `identify-assumptions` | Surface risky assumptions (4-risk or broader lens by stage) |
| `prioritize-assumptions` | Impact × Uncertainty matrix → test-first list |
| `brainstorm-experiments` | Cheapest valid tests for the top assumptions |
| `interview-script` | JTBD-style, non-leading interview guide |
| `survey-design` | Unbiased quantitative instrument + analysis plan |
| `summarize-interview` | Structured single-transcript summary |
| `synthesize-research` | Cross-source themes, insights, and implications |

## Commands
Workflow commands that orchestrate the skills above (methodology stays in the skills; commands sequence them, add checkpoints, and compile a consolidated deliverable).

| Command | Args | Orchestrates |
|---|---|---|
| `/discover` | `<problem or idea> [new\|existing]` | Full loop: frame → OST → ideate → prioritize-ideas → assumptions → prioritize → experiments |
| `/brainstorm` | `[ideas\|experiments] [new\|existing]` | Routes to the right ideation skill, then `prioritize-ideas` |
| `/validate` | `<idea or solution> [new\|existing]` | `identify-assumptions` → `prioritize-assumptions` → `brainstorm-experiments` |
| `/interview` | `[prep\|summarize\|synthesize]` | `interview-script` / `summarize-interview` / `synthesize-research` |

> Note: `plugin.json` uses standard Claude Code plugin fields; confirm against the current plugin spec when you install, as the schema may have moved since this was written.

## Author
Created by **Mohammad Hasan Rizvi**, co-authored by **Claude** (Anthropic).
