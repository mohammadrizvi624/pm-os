# pm-core

The foundation of the PM OS. Install this first — it defines the **company-context** layer every other plugin reads, ships the **pm-frameworks** the others reference, sets the **writing voice**, keeps a **decision log**, and provides the **pm-critic** review agent.

## Company-context contract
Every PM-OS skill reads company facts from `./company-context/*` in the host project, never hardcodes them, flags gaps as `[TODO: confirm]`, and saves work to `./outputs/`. Swap the context folder to reuse the whole OS at a different company. This plugin ships the blank templates (and the skill that explains/audits the layer); the filled-in `./company-context/` lives in your project root.

The context files — **templates** bundled at `skills/company-context/templates/`; the **live** `./company-context/` folder they scaffold into lives in *your project root*, not in the plugin:
`00-company` · `01-product` · **`02-product-team` ★** · `03-users-personas` · `04-market-competitors` · `05-metrics-goals` · `06-stakeholders` · `07-tools-stack` · `08-voice-tone` · `09-glossary`

`02-product-team` is the **primary operating context** — the immediate team's charter, ownership, members, goals/metrics, rituals, dependencies, and decision norms. When company-level and team-level context conflict, the team file governs day-to-day work.

## Skills
| Skill | Does |
|---|---|
| `company-context` | The contract: what each file holds, how skills consume it, how to audit it |
| `pm-frameworks` | Prioritization/scoring reference — RICE, ICE, Opportunity Score, Kano, MoSCoW, Value/Effort, Weighted Scoring, WSJF (referenced by six plugins) |
| `pm-writing-voice` | PM writing principles (BLUF, plain language) applied in the brand voice |
| `decision-log` | ADR-style decision records with supersede semantics |

## Agent
| Agent | Does |
|---|---|
| `pm-critic` | A sharp, fair reviewer for any PM artifact — steelmans then attacks load-bearing assumptions, ranks failure modes, hands back the cheapest test for each, and says plainly what's well-reasoned |

## Commands
| Command | Args | Orchestrates |
|---|---|---|
| `/context` | `[scaffold\|update\|audit]` | Stand up / edit / gap-check the `company-context` folder |
| `/onboard` | `[optional notes/docs]` | Onboarding interview for a new PM → populates the context (leads with the product team) |
| `/decision-log` | `[add\|list\|supersede]` | Record and maintain decisions over time |

## Why other plugins depend on this
`pm-frameworks` is referenced by discovery (`prioritize-ideas`, `prioritize-assumptions`, the opportunity-solution tree), execution (`prioritize-features`), and market-research (`feature-request-triage`) for the scoring math. Every plugin's skills read the context files defined here. pm-core is a declared dependency for the marketplace, not a domain plugin.

## Author
Created by **Mohammad Hasan Rizvi**, co-authored by **Claude** (Anthropic).
