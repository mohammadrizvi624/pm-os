# pm-data-analytics

Measurement-and-learning skills for the PM OS — instrumenting the product, analyzing behavioral data, running experiments, and turning results into decisions. Quantitative counterpart to discovery (qualitative research) and market-research (VoC/qualitative analysis).

## Company-context contract
Every skill reads company facts from `./company-context/*` (especially `05-metrics-goals.md` and `07-tools-stack.md` for the analytics/warehouse stack) and never hardcodes them. Missing context is flagged `[TODO: confirm]`. Deliverables save to `./outputs/`.

## Skills
| Skill | Does |
|---|---|
| `metrics-framework` | North Star + metric tree + guardrails (AARRR/HEART) |
| `tracking-plan` | Event/property instrumentation spec |
| `funnel-analysis` | Conversion + drop-off, biggest leak, by segment |
| `cohort-analysis` | Retention/engagement by cohort + follow-up research |
| `metric-investigation` | Root-cause a metric move (data integrity → decompose → rule in/out) |
| `experiment-design` | A/B design: hypothesis, MDE, sample size/power, pre-registered criteria |
| `experiment-analysis` | A/B readout: validity checks, significance, guardrails, ship/extend/stop |
| `dashboard-spec` | Ongoing KPI dashboard / metrics report spec |
| `sql-query` | Natural-language → optimized SQL (multi-dialect) with validation |

## Design notes (reconciliation with Huryn's set)
Huryn's analytics plugin had only 3 skills; this is a fuller 9.
- **Adopted:** `cohort-analysis` (his name + breadth — retention *and* engagement/adoption cohorts, plus the follow-up-research loop), `experiment-analysis` (his `ab-test-analysis` rigor — sample-size validation, SRM, CIs, the ship/extend/stop/investigate decision table), and `sql-query` (his `sql-queries` — this resolved a candidate I'd flagged).
- **Added (gaps he lacked):** `metrics-framework`, `tracking-plan`, `funnel-analysis`, `metric-investigation`, and `experiment-design` (he had A/B analysis but no design).
- **Left out:** `forecasting`/growth-model (no strong case from either side).

## Boundaries (what lives elsewhere)
- Quarterly target-setting (`okrs`) and the PRD success-metric target → `pm-execution`; this plugin owns the durable *measurement* model and the analysis.
- Cheap pre-build validation experiments (pretotypes, fake-doors) → `pm-discovery`'s `brainstorm-experiments`; `experiment-design` here is rigorous live-product A/B testing.
- Qualitative/VoC analysis, sentiment, segmentation → `pm-market-research`; `funnel`/`cohort` are the quantitative complements to its `customer-journey-map`.
- Prioritization frameworks (RICE/ICE) → `pm-core` `pm-frameworks`.

## Commands
Workflow commands over the skills. Methodology stays in the skills; commands route modes and sequence chains.

| Command | Args | Orchestrates |
|---|---|---|
| `/measure` | `[framework\|tracking\|dashboard\|full]` | `metrics-framework` / `tracking-plan` / `dashboard-spec`; `full` = model → instrument → monitor |
| `/analyze` | `[funnel\|cohort\|investigate\|query]` | `funnel-analysis` / `cohort-analysis` / `metric-investigation` / `sql-query` |
| `/experiment` | `[design\|analyze]` | `experiment-design` / `experiment-analysis` |

`dashboard-spec` is homed as the third step of `/measure` and `sql-query` as the `query` mode of `/analyze` (the data-pull that precedes an analysis) — so neither is a 1:1 wrapper. Huryn's three commands were per-skill wrappers (`analyze-cohorts`, `analyze-test`, `write-query`); they map onto `/analyze cohort`, `/experiment analyze`, and `/analyze query`. `/analyze` shares a short name with `pm-strategy`'s command but is namespaced (`pm-data-analytics:analyze`).

## Author
Created by **Mohammad Hasan Rizvi**, co-authored by **Claude** (Anthropic).
