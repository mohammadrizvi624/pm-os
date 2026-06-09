---
description: Create a comprehensive product strategy on the 9-section Product Strategy Canvas — from vision to defensibility.
argument-hint: "<product or scope> [new|existing]"
---

# /strategy — product strategy

Builds a complete strategy by chaining vision and value proposition into the 9-section Product Strategy Canvas, with checkpoints. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/strategy AI design tool for non-designers
/strategy existing: our analytics platform, annual planning
/strategy            # asks about your product
```

## Workflow

### 0 · Context
Parse `$ARGUMENTS` for the product and stage (`new`|`existing`; infer from `company-context/01-product.md` if absent). Confirm what triggered the strategy (new product, pivot, planning, fundraise). Read any attached strategy/pitch material.

### 1 · Vision
Apply **product-vision** (or reuse one from `./outputs/`).
▸ Checkpoint: confirm the vision before building on it.

### 2 · Value proposition
Apply **value-proposition** for the primary segment (6-part JTBD → statement).
▸ Optional: offer to run `/analyze scan` first if the strategic context isn't clear.

### 3 · Strategy canvas
Apply **product-strategy** for the 9 sections, pulling in the vision and value prop above. Validate coherence and flag the hypotheses that must hold.

### 4 · Compile
Save to `./outputs/<YYYY-MM-DD>_product-strategy_<slug>.md`:
```
## Product strategy: <name>
Date · Stage: <new|existing>

1. Vision — <inspiring, achievable, emotional; 2-3 sentences>
2. Target segments — | Segment | Size | Pain | Current alternative | Priority |  (+ who we explicitly don't serve)
3. Value proposition — per segment: what before → how → what after → alternatives
4. Trade-offs — | We choose | Over | Because |
5. Key metrics — North Star · input metrics · health/guardrails
6. Growth engine — acquire/activate/expand mechanisms (specific)
7. Capabilities — | Capability | Build/Buy/Partner | Investment | Timeline |
8. Defensibility — which moat (network effects, data, brand, switching costs, scale)
9. Coherence check + critical hypotheses (label early-stage ones)
Strategic risks: top 3 that could invalidate this.
```
Offer a one-page condensed version for execs.

### 5 · Next steps
In-plugin or generic only: "Build the business model behind it?" → `/business-model`; "Stress-test the assumptions?" → `/analyze scan`. Generically: once set, take the riskiest bets into discovery to validate, and turn Section 6 metrics into objectives in execution.

## Notes
- Strategy is about what you say NO to — push hard on trade-offs.
- Defensibility is the hardest section; it's fine to admit there's no real moat yet.
- References only `pm-strategy` skills.
