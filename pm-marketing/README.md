# pm-marketing

The unified commercial plugin for the PM OS — take the product to market and grow it. Combines what could be two plugins (go-to-market + marketing/growth) into one, with positioning/messaging as the shared spine so neither launch nor growth reaches across a plugin boundary for it.

## Company-context contract
Every skill reads company facts from `./company-context/*` and never hardcodes them. Missing context is flagged `[TODO: confirm]`. Deliverables save to `./outputs/`.

## Skills
**Positioning & messaging (shared spine)**
| Skill | Does |
|---|---|
| `positioning` | Differentiated positioning vs competitors → positioning statements |
| `messaging` | Audience-specific value-prop statements (marketing/sales/onboarding) |

**Go-to-market (launch)**
| Skill | Does |
|---|---|
| `icp` | Ideal Customer Profile + disqualification criteria |
| `beachhead` | First-segment selection (Crossing the Chasm, 4 criteria) |
| `gtm-strategy` | Launch plan: channels, messaging, metrics, phased timeline |
| `sales-enablement` | Competitive battlecards + objection handling |
| `product-naming` | Name candidates with rationale + trademark/domain notes |

**Growth**
| Skill | Does |
|---|---|
| `growth-loops` | 5 loop types (viral/usage/collaboration/UGC/referral) + coefficient |
| `acquisition-channels` | 7 GTM motions scored + motion stack + concrete ideas |
| `lifecycle-marketing` | Onboarding/activation/retention/re-engagement + change comms |

## Design notes (reconciliation with Huryn's two plugins)
Merged Huryn's go-to-market and marketing/growth skills into one set.
- **Adopted:** `beachhead-segment`→`beachhead`, `ideal-customer-profile`→`icp`, `positioning-ideas`→`positioning`, `value-prop-statements`→`messaging`, `competitive-battlecard`→`sales-enablement` (broadened), `growth-loops`, `gtm-strategy`, `product-name`→`product-naming`.
- **Evicted:** `north-star-metric` — duplicate of `pm-data-analytics`'s `metrics-framework` (NSM belongs to analytics).
- **Folded:** `gtm-motions` (the 7-motion framework) → into `acquisition-channels`, since it's fundamentally channel strategy, not the launch plan. `marketing-ideas` → also into `acquisition-channels` (concrete ideas per recommended channel).
- **Gap-adds (Huryn lacked):** `lifecycle-marketing` (retention/CRM campaigns). `acquisition-channels` itself is the durable channel-strategy home.
- **Dropped (my earlier candidate):** `conversion-optimization` (overlapped `acquisition-channels` and analytics' product `funnel-analysis`).

## Boundaries (what lives elsewhere)
- `value-proposition` (the value, JTBD) → `pm-strategy`; `positioning`/`messaging` here frame and articulate it for market.
- `monetization`/`pricing` → `pm-strategy`.
- Market-level *segments* → `pm-market-research`; ICP/beachhead (the target customer/first segment) here.
- North Star + metric tree, experiment rigor, product funnel/retention *measurement* → `pm-data-analytics`; `lifecycle-marketing` runs the campaigns, analytics measures them.
- Internal launch readiness (`pre-mortem`, `stakeholder-map`) and the `release-notes` changelog → `pm-execution`; `gtm-strategy` is the external launch.
- Growth-idea prioritization (ICE) → `pm-core` `pm-frameworks`.

## Commands
Workflow commands over the skills, organized around the brand spine + the two flows it feeds.

| Command | Args | Orchestrates |
|---|---|---|
| `/position` | `[positioning\|messaging\|naming\|full]` | `positioning` / `messaging` / `product-naming`; `full` = positioning → messaging |
| `/go-to-market` | `[icp\|beachhead\|plan\|battlecard\|full]` | `icp` / `beachhead` / `gtm-strategy` / `sales-enablement`; `full` = icp → beachhead → gtm-strategy |
| `/grow` | `[loops\|channels\|lifecycle\|full]` | `growth-loops` / `acquisition-channels` / `lifecycle-marketing`; `full` = channels → loops → lifecycle |

`product-naming` is homed in `/position` (per Huryn's "creative toolkit" grouping) rather than a 1:1 wrapper; `sales-enablement` is the `battlecard` mode of `/go-to-market`. `/go-to-market full` pulls messaging from `/position` and channels from `/grow` — clean because they're one plugin. Named `/go-to-market` (not `/launch`) to stay distinct from `pm-execution`'s internal `/launch`. Huryn's `north-star` command isn't replicated — its skill lives in `pm-data-analytics` (`/measure framework`).

## Author
Created by **Mohammad Hasan Rizvi**, co-authored by **Claude** (Anthropic).
