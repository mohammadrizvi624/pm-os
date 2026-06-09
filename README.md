# PM OS

A personal "AI operating system" for product management, built as a Claude Code plugin marketplace. It turns the recurring work of a PM — discovery, strategy, execution, go-to-market, growth — into reusable, high-quality workflows that stay grounded in *your* company's specific context.

> Status: all 7 plugins built and wired into `marketplace.json`. This README is a living document. Last updated: 2026-06-09 (full marketplace complete; next up: sub-agents — see roadmap).

## Purpose

PM OS is built on one idea: keep the **generic craft of product management** strictly separate from **company-specific facts**. The craft lives in reusable plugins; the facts live in a single swappable `company-context/` folder. Because no plugin hardcodes anything about your company, you can reuse the entire system at a different company by replacing that one folder — and changing nothing else.

## When to use it

Reach for PM OS whenever you're doing product work and want it done with rigor and consistency rather than from a blank page — discovery, product strategy, specs and delivery, market research, data and analytics, go-to-market, and product marketing. All seven domains are built and installable today; sub-agents are the main item still on the roadmap below.

## How it works

### Two layers

```
GENERIC PM LAYER  (reusable, company-agnostic)
  plugins  ->  skills + commands
       |   every skill reads from  v
COMPANY-CONTEXT LAYER   ./company-context/     <-- swap this per company
       |   deliverables saved to  v
  ./outputs/
```

### Three building blocks

- **Skills** — atomic, model-invoked know-how plus templates for a single PM task (skills are *nouns*). They auto-trigger when relevant to the conversation.
- **Commands** — *verb* workflows (`/discover`, `/validate`) that orchestrate several skills with checkpoints and compile a consolidated deliverable. The methodology stays in the skills; commands sequence them.
- **Sub-agents** — specialist workers with their own context window for heavy or focused work (e.g. a research agent, a reviewer). `pm-core` ships the `pm-critic` review agent today; more are on the roadmap.

### The company-context contract

Every skill reads company facts from `./company-context/*` in the host project, never hardcodes them, and flags anything missing as `[TODO: confirm]` instead of inventing it. Every deliverable is saved to `./outputs/`. This contract is what makes the system swappable.

The context layer (templates shipped by `pm-core`):

| File | Holds |
|---|---|
| `00-company.md` | Company, mission, business model, stage |
| `01-product.md` | Product(s), value, architecture, stage |
| `02-product-team.md` ★ | **The immediate product team** — charter, ownership, members/roles, team goals & metrics, rituals, dependencies, decision norms (primary operating context) |
| `03-users-personas.md` | Users/buyers, personas, jobs-to-be-done |
| `04-market-competitors.md` | Market, segments, competitors |
| `05-metrics-goals.md` | North Star, KPIs, current goals/OKRs |
| `06-stakeholders.md` | Who's who, decision rights |
| `07-tools-stack.md` | Tooling (Jira, analytics, design) + conventions |
| `08-voice-tone.md` | Writing voice for users & stakeholders |
| `09-glossary.md` | Internal terms, acronyms, product names |

### Conventions

- Skills are nouns (domain knowledge); commands are verbs (workflows).
- A skill's name matches its directory name.
- Skills declare `name` + `description`; commands declare `description` + `argument-hint`.
- No cross-plugin references in commands, so each plugin installs and runs independently.

## How to use it

1. Open your work project in Claude Code (VS Code, desktop, or CLI).
2. Add this marketplace, then install the plugins you need (always install `pm-core` first):
   ```
   /plugin marketplace add mohammadrizvi-ls-bit/pm-os      # or a local path: /plugin marketplace add /path/to/pm-os_x
   /plugin install pm-core@pm-os
   /plugin install pm-discovery@pm-os                       # add any of the other six the same way
   ```
   (You can also browse and toggle plugins interactively with `/plugin`.)
3. Create a `company-context/` folder in your project and fill it in — or run `/onboard` (pm-core) to populate it by interview, starting with `02-product-team.md` (the most-used context). Partial is fine — workflows flag gaps rather than guess.
4. Do the work: run a command (e.g. `/discover in-app onboarding checklist`) or just ask in plain language and the relevant skill auto-triggers.
5. Find deliverables in `./outputs/`.

To reuse at another company: copy the project, replace `company-context/`, change nothing else.

## Plugins

| Plugin | Purpose | Status |
|---|---|---|
| `pm-core` | Foundation: company-context layer + templates, shared `pm-frameworks` (RICE/ICE/Opportunity Score, Kano, MoSCoW, Value/Effort, Weighted, WSJF), writing voice, decision log, and the `pm-critic` agent | **Built — v0.1.0** |
| `pm-discovery` | Discovery: framing, opportunity-solution trees, ideation, assumptions, experiments, interviews, research synthesis | **Built — v1.1.0** |
| `pm-strategy` | Vision, Product Strategy Canvas, BMC/Lean canvases, value prop, SWOT/PESTLE/Porter/Ansoff, monetization & pricing | **Built — v0.2.0** |
| `pm-execution` | PRDs, user stories, feature prioritization, outcome roadmaps, OKRs, pre-mortems, stakeholder maps, release notes | **Built — v0.3.0** |
| `pm-market-research` | Personas, journey maps, market & user segmentation, sizing (TAM/SAM/SOM), competitor analysis, sentiment, request triage | **Built — v0.2.0** |
| `pm-data-analytics` | Metric frameworks, tracking plans, funnel & cohort analysis, metric investigation, experiment design & analysis, dashboards, SQL | **Built — v0.2.0** |
| `pm-marketing` | Positioning, messaging, ICP, beachhead, GTM strategy, sales enablement, naming, growth loops, acquisition channels, lifecycle | **Built — v0.2.0** |

## pm-discovery (built)

Twelve skills running as a pipeline, plus four orchestration commands. See `pm-discovery/README.md` for full detail.

Pipeline: `frame-problem` -> `opportunity-solution-tree` -> `brainstorm-new-product` | `brainstorm-features` -> `prioritize-ideas` -> `identify-assumptions` -> `prioritize-assumptions` -> `brainstorm-experiments` -> `interview-script` -> `survey-design` -> `summarize-interview` -> `synthesize-research`

Skills:

| Skill | Does |
|---|---|
| `frame-problem` | Define the problem/opportunity before solutioning |
| `opportunity-solution-tree` | Map outcome -> opportunities -> solutions -> experiments |
| `brainstorm-new-product` | Greenfield (initial-discovery) ideation |
| `brainstorm-features` | Bounded (continuous-discovery) ideation for a live product |
| `prioritize-ideas` | Narrow ideas to a validate-next shortlist (exploratory criteria) |
| `identify-assumptions` | Surface risky assumptions (4 core risks, or 8 for new products) |
| `prioritize-assumptions` | Impact x Uncertainty matrix -> test-first list |
| `brainstorm-experiments` | Cheapest valid tests for the leap-of-faith assumptions |
| `interview-script` | Mom Test-based interview guide + note template |
| `survey-design` | Unbiased quantitative instrument + analysis plan |
| `summarize-interview` | Structured single-transcript summary |
| `synthesize-research` | Cross-source themes, insights, and implications |

Commands:

| Command | Args | Orchestrates |
|---|---|---|
| `/discover` | `<problem or idea> [new\|existing]` | Full loop: frame -> OST -> ideate -> prioritize-ideas -> assumptions -> prioritize -> experiments |
| `/brainstorm` | `[ideas\|experiments] [new\|existing]` | Routes to the right ideation skill, then `prioritize-ideas` |
| `/validate` | `<idea or solution> [new\|existing]` | `identify-assumptions` -> `prioritize-assumptions` -> `brainstorm-experiments` |
| `/interview` | `[prep\|summarize\|synthesize]` | `interview-script` / `summarize-interview` / `synthesize-research` |

## pm-strategy (built)

Eleven skills plus four commands, covering the "where to play / how to win" thinking. See `pm-strategy/README.md` for detail.

Skills: `product-vision` · `product-strategy` (9-section canvas, Rumelt-disciplined) · `business-model-canvas` · `lean-canvas` · `value-proposition` (6-part JTBD) · `swot-analysis` · `pestle-analysis` · `porters-five-forces` · `ansoff-matrix` · `monetization-strategy` · `pricing-strategy`

Commands:

| Command | Args | Orchestrates |
|---|---|---|
| `/strategy` | `<product or scope> [new\|existing]` | vision → value-prop → 9-section strategy canvas |
| `/analyze` | `[swot\|pestle\|five-forces\|ansoff\|scan]` | a single lens, or `scan` = all four synthesized |
| `/business-model` | `[bmc\|lean]` | Business Model Canvas vs Lean Canvas |
| `/monetize` | `[model\|pricing\|full]` | monetization-strategy / pricing-strategy / chain |

## pm-market-research (built)

Eight skills plus three commands — understanding the market, customers, and competitors. See `pm-market-research/README.md`.

Skills: `user-personas` · `customer-journey-map` · `market-segmentation` (top-down) · `user-segmentation` (bottom-up from data) · `market-sizing` (TAM/SAM/SOM) · `competitor-analysis` · `sentiment-analysis` (scoped to sentiment/satisfaction) · `feature-request-triage`

Commands:

| Command | Args | Orchestrates |
|---|---|---|
| `/research-users` | `[personas\|segment\|journey\|all]` | personas / user-segmentation / journey map |
| `/analyze-feedback` | `[sentiment\|requests\|full]` | sentiment then request triage |
| `/market` | `[segments\|sizing\|competitors\|scan]` | market segments / sizing / competitors, or all three |

## pm-execution (built)

Eight skills plus three commands — turning validated strategy/discovery into specified, prioritized, shipped product. His 16 skills pruned to a lean 8 (story formats and the two adversarial reviews merged; the prioritization reference moved to pm-core; dev/QA/ceremony skills cut). See `pm-execution/README.md`.

Skills: `prd` · `user-stories` (3 C's + INVEST; classic or job-story) · `prioritize-features` (RICE/ICE via pm-core) · `roadmap` (outcome-focused) · `okrs` · `pre-mortem` (assumption attack + Tiger/Paper-Tiger/Elephant + cheapest test) · `stakeholder-map` · `release-notes`

Commands:

| Command | Args | Orchestrates |
|---|---|---|
| `/plan` | `[okrs\|roadmap\|prioritize\|full]` | okrs → roadmap → prioritize |
| `/spec` | `[prd\|stories\|premortem\|full]` | prd → pre-mortem → stories |
| `/launch` | `[premortem\|stakeholders\|notes\|full]` | pre-mortem → stakeholder-map → release-notes |

## pm-data-analytics (built)

Nine skills plus three commands — the quantitative measurement-and-learning layer. Huryn's sparse 3 skills expanded to a full 9 (his cohort, A/B analysis, and SQL adopted; metric model, tracking, funnels, investigation, and experiment *design* added). See `pm-data-analytics/README.md`.

Skills: `metrics-framework` · `tracking-plan` · `funnel-analysis` · `cohort-analysis` · `metric-investigation` · `experiment-design` · `experiment-analysis` · `dashboard-spec` · `sql-query`

Commands:

| Command | Args | Orchestrates |
|---|---|---|
| `/measure` | `[framework\|tracking\|dashboard\|full]` | model → instrument → monitor |
| `/analyze` | `[funnel\|cohort\|investigate\|query]` | pull data + funnel/cohort/diagnose |
| `/experiment` | `[design\|analyze]` | A/B design and readout |

## pm-marketing (built)

Ten skills plus three commands — the unified commercial plugin (go-to-market + marketing/growth merged into one, so positioning/messaging is a shared spine rather than a cross-plugin dependency). See `pm-marketing/README.md`.

Skills: `positioning` · `messaging` · `icp` · `beachhead` · `gtm-strategy` · `sales-enablement` · `product-naming` · `growth-loops` · `acquisition-channels` (folds Huryn's gtm-motions + marketing-ideas) · `lifecycle-marketing`. (`north-star-metric` evicted → it's `pm-data-analytics`'s `metrics-framework`.)

Commands:

| Command | Args | Orchestrates |
|---|---|---|
| `/position` | `[positioning\|messaging\|naming\|full]` | positioning → messaging (+ naming) |
| `/go-to-market` | `[icp\|beachhead\|plan\|battlecard\|full]` | icp → beachhead → gtm-strategy (+ battlecard) |
| `/grow` | `[loops\|channels\|lifecycle\|full]` | channels → loops → lifecycle |

## pm-core (built)

The foundation, built last but installed first. Four skills, three commands, one agent, and the ten context templates. See `pm-core/README.md`.

Skills: `company-context` (the contract + audit) · `pm-frameworks` (RICE/ICE/Opportunity Score/Kano/MoSCoW/Value-Effort/Weighted/WSJF — referenced by six plugins) · `pm-writing-voice` · `decision-log`.

Agent: `pm-critic` — a fair adversarial reviewer for any PM artifact (steelman → attack load-bearing assumptions → rank → cheapest test + kill criteria), the project's one sub-agent.

Commands:

| Command | Args | Does |
|---|---|---|
| `/context` | `[scaffold\|update\|audit]` | manage the company-context folder |
| `/onboard` | `[notes/docs]` | new-PM interview → fills the context (leads with the product team) |
| `/decision-log` | `[add\|list\|supersede]` | record & maintain decisions |

Ships the ten context templates (`00`–`09`, including the new `02-product-team` ★) and the `marketplace.json` that ties all seven plugins together.

## Roadmap

- [x] `pm-discovery` — 12 skills, 4 commands
- [x] `pm-strategy` — 11 skills, 4 commands
- [x] `pm-market-research` — 8 skills, 3 commands
- [x] `pm-execution` — 8 skills, 3 commands
- [x] `pm-data-analytics` — 9 skills, 3 commands
- [x] `pm-marketing` — 10 skills, 3 commands (merged go-to-market + marketing/growth)
- [x] `pm-core` — 4 skills, 3 commands, 1 agent (pm-critic), 10 context templates
- [x] `pm-critic` review agent (in `pm-core/agents/`)
- [ ] Additional sub-agents: `discovery-researcher`, `competitive-analyst`, `data-analyst`, `qa-engineer`
- [x] Marketplace manifest (`marketplace.json`) wiring all 7 plugins
- [x] Root cleanup — stale turn-1 flat-structure files removed

Parked items — all now placed: Opportunity Score / ICE / RICE → `pm-core` `pm-frameworks`; `prioritize-features` → `pm-execution`; `analyze-feature-requests` → `feature-request-triage` in `pm-market-research`; the `pm-critic` agent → `pm-core`. The build is complete; all 7 plugins are wired into `marketplace.json`.

## Author

Created by **Mohammad Hasan Rizvi**, co-authored by **Claude** (Anthropic).
