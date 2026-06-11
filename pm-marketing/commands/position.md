---
description: Frame the product for market — positioning, audience messaging, and naming. The brand spine that feeds launch and growth.
argument-hint: "[positioning|messaging|naming|full] <product>"
---

# /position — position & message

Routes a single brand/presentation skill, or `full` chains positioning into messaging. Underlying skills load `./company-context/*` and save to `./outputs/`.

## Invocation
```
/position full our analytics product vs enterprise incumbents
/position positioning differentiate from Notion
/position messaging [reuse our value proposition]
/position naming the new developer feature
/position            # asks what you need
```

## Modes
Parse `$ARGUMENTS` for the mode and target.
- `positioning` → **positioning** (competitive landscape → differentiated positioning statements)
- `messaging` → **messaging** (audience-specific value-prop statements)
- `naming` → **product-naming**
- `full` (default) → positioning → messaging (lock the angle, then write the words).

## Output (`full`)
Save to `./outputs/<YYYY-MM-DD>_positioning-messaging_<slug>.md`:
```
Positioning options (vs competitors) → recommended angle + why
Value-prop copy: tagline · elevator pitch · landing hero · sales one-liner
Messaging matrix: | Audience | Key message | Proof point | CTA |
```

## Next steps
In-plugin: "Take it to launch?" → `/go-to-market`; "Build the growth engine?" → `/grow`.

## Notes
- This is the brand spine the other two commands draw on — positioning frames strategy's value proposition for market.
- References only `pm-marketing` skills.
