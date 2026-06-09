---
name: identify-assumptions
description: "Surface the risky assumptions behind an idea, feature, or product concept. Use before committing to build or experiments, to expose what must be true. Adapts automatically — existing features get the four core product risks; new products get the broader eight. Pairs with prioritize-assumptions and brainstorm-experiments."
---
# Identify assumptions

Devil's-advocate analysis that surfaces what must be true for an idea to succeed, so the riskiest beliefs get tested before investment. The goal is to strengthen the idea, not kill it — good teams expect roughly 3 in 4 ideas to underperform, so surface the risks early. Four core product risks: Teresa Torres / Marty Cagan.

## Inputs
- The idea, feature, or concept to stress-test. If designs, PRDs, or research are attached, read them first.

## Load company context
Read `./company-context/01-product.md` (to determine stage), `03-users-personas.md`, `05-metrics-goals.md`.

## Choose the lens (from product stage)
- Existing feature → the four core product risks only.
- New product / 0-to-1 → the four core PLUS Ethics, Go-to-Market, Strategy, and Team.
Infer stage from `01-product.md`; if ambiguous, ask once. State which lens you used.

## Surface from three angles
Run a devil's-advocate pass asking why this might fail, from each: PM (demand, willingness to pay, competition, strategic fit), Designer (first-time experience, onboarding, adoption, cognitive load), Engineer (feasibility, build-vs-buy, scalability, integration, tech debt).

## Risk categories (with prompts)
Core (always):
- Value — does it solve a real problem; will they keep using it?
- Usability — can they figure it out; is onboarding fast enough; does it add cognitive load?
- Viability — can we sell/monetize/finance/support/scale it; is it compliant?
- Feasibility — can we build it with current tech; are integrations possible; can it scale efficiently?

Additional (new product only):
- Ethics — should we build it at all; does it pose any risk to customers?
- Go-to-Market — do we have the channels; is the messaging/timing/launch motion right?
- Strategy & objectives — can others copy it; have we weighed PESTLE factors; are these the right problems to solve?
- Team — right people, tools, and collaboration; will the team stay long enough?

## Method
1. Under each relevant category, write falsifiable "We assume that …" statements — specific about who, what behavior, and roughly how much. ("Users will adopt it" is too vague.)
2. Separate evidence-backed assumptions from leaps of faith.
3. (Confidence rating and test selection happen next, in `prioritize-assumptions`.)

## Output
Save to `./outputs/<YYYY-MM-DD>_assumptions_<slug>.md`. Template:
```
Lens used: 4-core (existing) | 8 (new product)
Value:        - We assume that … [evidence | leap]
Usability:    - We assume that … [leap]
Feasibility:  - …
Viability:    - …
(new product also:)
Ethics / Go-to-Market / Strategy / Team: - We assume that … [leap]
```
Example: "Value — We assume that ≥30% of Operations leads will trust auto-matched line items without manual review. [leap]"

## Avoid
- Vague, untestable assumptions.
- Treating evidence-backed and unevidenced assumptions the same.
- Using the pass to kill the idea rather than strengthen it.
