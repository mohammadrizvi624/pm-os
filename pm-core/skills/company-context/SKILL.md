---
name: company-context
description: "The company-context contract for the PM OS — what each context file holds, how skills consume it, and how to keep it current and gap-checked. Use when setting up, auditing, or updating the ./company-context folder, or to understand how context flows into every other skill."
---
# Company context

The company-context layer is the swappable folder that makes every PM-OS skill specific to *your* company without hardcoding anything. Skills read these files, never invent facts, flag gaps as `[TODO: confirm]`, and save work to `./outputs/`. Swap the folder to reuse the whole OS at a different company.

## Where these live (important)
- **Live context** — the filled-in `./company-context/` folder that skills read at runtime — lives in **your project root** (the repo where you run Claude Code), *not* inside any plugin. It's your company's swappable layer.
- **Templates** — blank starters for those files — are bundled with this plugin at `skills/company-context/templates/`. `/context scaffold` and `/onboard` copy them into your project's `./company-context/`. You don't edit the bundled templates; you fill in the copy in your project.

## The files (`./company-context/`)
- `00-company.md` — the wider company: mission, business model, strategy, org shape, stage.
- `01-product.md` — the product: what it is, surfaces, how it works, current state.
- `02-product-team.md` — **the immediate product team (the most-used context).** Team charter/mission, what the team owns (scope/surface), members & roles (PM, eng, design, data, etc.), the team's goals/OKRs and metrics, rituals & ways of working (ceremonies, cadences), key dependencies/adjacent teams, and decision-making norms. When company-level and team-level context conflict, the team file governs day-to-day work.
- `03-users-personas.md` — users, segments, personas.
- `04-market-competitors.md` — market, competitors, differentiation.
- `05-metrics-goals.md` — North Star, key metrics/KPIs, current goals/targets.
- `06-stakeholders.md` — stakeholders beyond the immediate team (leadership, partners, adjacent functions).
- `07-tools-stack.md` — tools and stack (analytics, tracker, warehouse, comms).
- `08-voice-tone.md` — brand/writing voice and tone.
- `09-glossary.md` — internal terms, acronyms, product nouns.

## How skills consume it
Each skill's "Load company context" step reads the files most relevant to it (e.g. `okrs` reads `00`, `02`, `05`). The contract: read what's there, treat `02-product-team.md` as the primary operating context, never hardcode facts, flag missing pieces as `[TODO: confirm]` rather than guessing, and write deliverables to `./outputs/`.

## Auditing
A good context file is specific, current, and sourced. Audit for: stale facts, empty/placeholder sections, missing metrics or team goals, and conflicts between the company and team files. Surface gaps as a checklist the user can fill (the `/onboard` command does this via interview; `/context audit` does it against existing files).

## Avoid
- Treating context as static — it drifts; re-audit when the team, product, or goals change.
- Letting a skill invent a fact that belongs in context — flag it for confirmation instead.
