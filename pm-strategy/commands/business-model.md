---
description: Build a business model — Business Model Canvas (established) or Lean Canvas (new venture).
argument-hint: "[bmc|lean] <product or business>"
---

# /business-model — business model

Routes between the two business-model canvases. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/business-model bmc our enterprise analytics platform
/business-model lean marketplace for freelance PMs
/business-model            # picks by stage, or asks
```

## Modes
Parse `$ARGUMENTS` for the mode and the product.
- `bmc` → **business-model-canvas** (Osterwalder, 9 blocks) — best for established products, strategic planning, investor materials.
- `lean` → **lean-canvas** (Maurya) — best for new ventures and hypothesis testing.
If no mode is given, pick by stage from `company-context/01-product.md` (`existing` → bmc, `new` → lean) and state the choice.

## Workflow
1. Confirm product, stage, and target customer; read any attached material.
2. Apply the chosen skill to produce the full canvas — for `lean`, add riskiest assumptions + validation experiments; for `bmc`, add an economic-viability check (e.g. LTV > ~3× CAC) and key risks.
3. Save to `./outputs/<YYYY-MM-DD>_<bmc|lean-canvas>_<slug>.md`.

## Next steps
In-plugin/generic: "Stress-test it?" → `/analyze scan`; "Price the revenue streams?" → `/monetize`; "Wrap a strategy around it?" → `/strategy`.

## Notes
- BMC lacks vision/trade-offs/metrics — those belong in `/strategy`; use BMC to show how the operational pieces connect.
- Lean Canvas is a fast hypothesis tool, not a finished strategy.
- References only `pm-strategy` skills.
