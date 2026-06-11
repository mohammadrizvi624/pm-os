# Changelog

All notable changes to PM OS are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and PM OS uses a **single, lockstep version** across the marketplace and all
seven plugins (see [Versioning](README.md#versioning)). It adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] — 2026-06-11

First versioned release. All seven plugins are wired into
`.claude-plugin/marketplace.json` and aligned to a single marketplace version.

### Added
- `pm-core` — foundation: company-context layer + 10 templates (`00`–`09`,
  incl. `02-product-team`), shared `pm-frameworks`, PM writing voice, decision
  log, and the `pm-critic` review agent.
- `pm-discovery` — problem framing, opportunity-solution trees, idea & assumption
  prioritization, experiments, interviews, surveys, and research synthesis.
- `pm-strategy` — vision, Product Strategy Canvas, business-model & lean canvases,
  value proposition, SWOT/PESTLE/Porter/Ansoff, monetization & pricing.
- `pm-market-research` — personas, journey maps, market & user segmentation,
  market sizing (TAM/SAM/SOM), competitor analysis, sentiment, feature-request triage.
- `pm-execution` — PRDs, user stories, feature prioritization, outcome roadmaps,
  OKRs, pre-mortems, stakeholder maps, and release notes.
- `pm-data-analytics` — metric frameworks, tracking plans, funnel & cohort analysis,
  metric investigation, experiment design & analysis, dashboards, and SQL.
- `pm-marketing` — positioning, messaging, ICP, beachhead, GTM strategy, sales
  enablement, naming, growth loops, acquisition channels, and lifecycle.

### Changed
- Aligned all plugin versions to a single lockstep `1.0.0` (previously ranged
  from `0.1.0` to `1.1.0`).

[Unreleased]: https://github.com/mohammadrizvi-ls-bit/pm-os/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/mohammadrizvi-ls-bit/pm-os/releases/tag/v1.0.0
