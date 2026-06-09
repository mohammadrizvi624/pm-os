---
name: acquisition-channels
description: "Choose and prioritize acquisition motions/channels across the 7 GTM motions — Inbound, Outbound, Paid, Community, Partners, ABM, PLG — and generate concrete, cost-effective ideas for the top picks. Use when selecting marketing channels, choosing inbound vs outbound vs PLG, or planning campaigns."
---
# Acquisition channels

Scores the acquisition motions that fit the product, recommends a focused stack of 2-4, and turns the top picks into concrete, cost-effective campaign ideas.

## Inputs
- The product, target customer, price point/ACV, sales-cycle length, team size, and budget. Read attached files first.

## Load company context
Read `./company-context/00-company.md` (business/revenue model, ACV), `03-users-personas.md`, `07-tools-stack.md`, `05-metrics-goals.md`.

## Method
1. Characterize the product economics: ACV, sales-cycle length, buyer/decision unit, self-serve potential.
2. Score the **7 GTM motions** for fit (1-10): **Inbound** (content/SEO), **Outbound** (cold/sales), **Paid digital**, **Community**, **Partners**, **ABM**, **PLG** — each with typical tools and best-fit context.
3. Recommend a **motion stack** of 2-4: one primary + complementary secondaries, with sequencing (which first) and rough resource split. (Paid funds growth; organic builds long-term value; PLG lowers CAC.)
4. For the top picks, generate ~5 concrete, cost-effective campaign ideas — each with channel, core message, why it works, and what makes it cost-efficient.

## Output
Save to `./outputs/<YYYY-MM-DD>_acquisition-channels_<slug>.md`:
```
7-motion fit scores (with reasoning)
Recommended motion stack (primary + secondary) · sequencing · resource split
Concrete ideas for the top channels: channel · message · why it works · cost-efficiency
90-day execution plan · success metric per motion
```

## Avoid
- Many channels done poorly — focus on a few executed well.
- Ignoring economics: match the motion to ACV and sales cycle (ABM for enterprise, PLG for low-ACV self-serve).
