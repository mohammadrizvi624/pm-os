# CLAUDE.md — PM OS 

## What this repo is
A Claude Code plugin marketplace: seven plugins + `.claude-plugin/marketplace.json`. Users install these into *their own* work project and point them at a `./company-context/` folder that lives there. Author: **Mohammad Hasan Rizvi**, co-authored by Claude.

## Two-layer architecture (do not mix the layers)
- **Generic PM layer** = the plugins here (skills + commands + agents). Company-agnostic. Never hardcode company facts.
- **Company-context layer** = a swappable `./company-context/*` folder in the *user's work project*, read by skills at runtime. It does **not** live in this repo. `pm-core` only ships the blank templates for it.

## Repo structure
```
.claude-plugin/marketplace.json     # registers all 7 plugins (pm-core first)
README.md                           # living overview of the whole OS
pm-core/                            # foundation — install first
  .claude-plugin/plugin.json
  skills/<skill>/SKILL.md
  skills/company-context/templates/ # the 10 blank context templates pm-core ships
  commands/<command>.md
  agents/pm-critic.md
pm-discovery/ pm-strategy/ pm-market-research/
pm-execution/ pm-data-analytics/ pm-marketing/   # same shape (skills/ + commands/ + README)
```

## Conventions (follow these when adding or editing)
- **Skills are nouns; commands are verbs.** One skill per directory; the skill's `name` equals its directory name.
- **Skill `SKILL.md`**: YAML frontmatter (`name`, `description` — write the description so the model knows *when* to invoke it). Body sections: a short intro, then `Load company context` → `Method` → `Output` → `Avoid` (add `Inputs` where useful). Keep it method-and-substance, not promo.
- **Commands route or chain — never 1:1-wrap a single skill.** A command either routes modes (`[mode-a|mode-b|full]` parsed from `$ARGUMENTS`) or chains ≥2 skills. Frontmatter: `description` + `argument-hint`.
- **No cross-plugin references** in any plugin's skills/commands — **except `pm-core`**, the one allowed shared dependency. (e.g. prioritization skills reference `pm-core`'s `pm-frameworks`.) This keeps every plugin independently installable.
- **Company-context contract** — every skill: reads `./company-context/*` (treat `02-product-team.md` as primary operating context), never hardcodes facts, flags gaps as `[TODO: confirm]`, and saves deliverables to `./outputs/`. Both paths are relative to the *user's* project, not this repo.

## pm-core specifics
- Ships the 10 context templates at `skills/company-context/templates/` (`00`–`09`, incl. `02-product-team` ★). These are copied into the user's project by `/onboard` and `/context scaffold` — the live folder is never created here.
- `pm-frameworks` (RICE/ICE/Opportunity Score/Kano/MoSCoW/Value-Effort/Weighted/WSJF) is referenced by six plugins for scoring math.
- `pm-critic` (the only agent) lives in `pm-core/agents/`; agents are plugin components and can't live at the repo root.

## Adding a plugin
1. Create `<plugin>/.claude-plugin/plugin.json` (`name`, `version`, `description`, `author`, `category`), plus `skills/`, `commands/`, `README.md`. Set `version` to the repo's current lockstep version — all plugins and `marketplace.json` share one version (see README → Versioning); bump them together and add a `CHANGELOG.md` entry.
2. Follow the conventions above; only reference `pm-core` across plugins.
3. Register it in `.claude-plugin/marketplace.json` (`name` + `source: "./<plugin>"` + `description`). Keep `pm-core` first.
4. Validate JSON; update the top-level `README.md`.

## Packaging
Per-plugin zips and a full-repo bundle (`pm-os.zip`) are produced into the outputs directory. The full bundle is the whole installable tree including `marketplace.json`.
