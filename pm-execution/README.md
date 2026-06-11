# pm-execution

Delivery skills for the PM OS — turning validated strategy and discovery into specified, prioritized, shipped product. Defining what to build, planning it, de-risking it, and shipping it.

## Company-context contract
Every skill reads company facts from `./company-context/*` in the host project and never hardcodes them. Missing context is flagged `[TODO: confirm]` rather than invented. Deliverables save to `./outputs/`.

## Skills
| Skill | Does |
|---|---|
| `prd` | Product requirements doc — 8-section spec, problem → release plan |
| `user-stories` | Stories with acceptance criteria (3 C's + INVEST; classic or job-story format) |
| `prioritize-features` | Rank & sequence the delivery backlog via RICE/ICE |
| `roadmap` | Outcome-focused roadmap (now/next/later), not a dated feature list |
| `okrs` | Team OKRs aligned to company objectives (three alternative sets) |
| `pre-mortem` | Stress-test a plan: attack assumptions, rank failure modes, cheapest test + kill criteria |
| `stakeholder-map` | Power × Interest grid + per-quadrant communication plan |
| `release-notes` | User-facing release notes / changelog from tickets/PRDs |

## Design notes (reconciliation with Huryn's set)
Huryn's `pm-execution` had 16 skills; this is a deliberately leaner 8.
- **Merged:** `user-stories` + `job-stories` + `wwas` → one `user-stories` (job-story framing folded in as an option). `pre-mortem` + `strategy-red-team` → one `pre-mortem` (pre-mortem's Tiger/Paper-Tiger/Elephant taxonomy + the red-team's steelman-and-attack rigor with cheapest-test/kill-criteria). `outcome-roadmap` → folded into a general `roadmap`.
- **Moved out:** `prioritization-frameworks` (the RICE/ICE reference) → `pm-core`'s `pm-frameworks`; `prioritize-features` here is the *action* that uses it.
- **Cut (wrong owner / out of scope):** `dummy-dataset` (dev/QA utility), `test-scenarios` (QA), `retro` (Scrum-Master ceremony), `sprint-plan` (EM/delivery-management), `summarize-meeting` (too generic; discovery already has `summarize-interview`).


- **Enriched from Huryn's command files (skills, not commands):** the command *structure* is unchanged, but useful methodology from his command bodies now lives in the skills — `prd` gains Non-Goals + a success-metrics table + P0/P1/P2 tiers + open questions; `okrs` gains an alignment map, scoring guide, check-in cadence, and gaming counter-metrics; `stakeholder-map` gains a stance column, escalation path, and RACI; `pre-mortem` gains a Go/No-Go checklist; `roadmap`, `user-stories`, and `release-notes` gain transformation notes, story-map/spike tagging, and Highlights/Coming-soon respectively.

## Boundaries (what lives elsewhere)
- RICE/ICE/Opportunity Score reference → `pm-core` `pm-frameworks`
- Experiment readouts, dashboards, metric deep-dives → `pm-data-analytics` (execution only *defines* success metrics, inside the PRD)
- Launch campaigns & messaging → `pm-marketing` (`release-notes` is the delivery changelog)
- Writing voice → `pm-core` `pm-writing-voice`
- `pre-mortem` is a technique skill; the planned `pm-core` `pm-critic` agent may later orchestrate it.

## Commands
Workflow commands across the delivery lifecycle (plan → spec → launch). Methodology stays in the skills; commands route modes and sequence chains.

| Command | Args | Orchestrates |
|---|---|---|
| `/plan` | `[okrs\|roadmap\|prioritize\|full]` | `okrs` / `roadmap` / `prioritize-features`; `full` = okrs → roadmap → prioritize |
| `/spec` | `[prd\|stories\|premortem\|full]` | `prd` / `user-stories` / `pre-mortem`; `full` = prd → pre-mortem → stories |
| `/launch` | `[premortem\|stakeholders\|notes\|full]` | `pre-mortem` / `stakeholder-map` / `release-notes`; `full` = pre-mortem → map → notes |

`pre-mortem` appears in both `/spec` (attack the PRD's assumptions early, while tests are cheap) and `/launch` (pre-ship risk pass on the launch plan) — same merged skill, two lenses, two moments. Huryn's execution commands were mostly per-skill wrappers plus a `/sprint` router — we don't replicate that pattern, and his commands for cut skills (`generate-data`, `meeting-notes`, `test-scenarios`, `sprint`'s plan/retro) are dropped.

## Author
Created by **Mohammad Hasan Rizvi**, co-authored by **Claude** (Anthropic).
