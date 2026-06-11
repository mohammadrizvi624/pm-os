---
name: icp
description: "Define the Ideal Customer Profile from research/PMF data — firmographics, behaviors, JTBD, pains — plus the disqualification criteria for who is NOT a fit. Use when defining your ICP, analyzing PMF survey data, or focusing sales/marketing on the best-fit customers. (Picks the target *account/customer*; market-level segments are pm-market-research.)"
---
# Ideal customer profile (ICP)

Synthesizes research into the customer most likely to find value, retain, and expand — the focus that aligns marketing, sales, and product. Distinct from market-level segmentation (that's `pm-market-research`); this names the best-fit *customer/account* and who to disqualify.

## Inputs
- Research/PMF data: survey responses, interview transcripts, customer-success/usage data, win-loss. Read attached files first.

## Load company context
Read `./company-context/03-users-personas.md`, `04-market-competitors.md`, and `05-metrics-goals.md` (LTV/retention signals).

## Method
1. Segment customers by value — highest LTV, fastest time-to-value, lowest churn, best expanders, strongest references — and study the winners.
2. Profile **firmographics/demographics** (size, industry, geography, role, budget authority).
3. Map **behaviors** (how they discover/evaluate/buy, decision unit, adoption speed).
4. Articulate **JTBD** (functional, emotional, social) and success criteria.
5. Document **pains/needs** (before → desired after, impact, budget).
6. State **disqualification criteria** (who is NOT a fit) and the "ideal-of-the-ideal" high-value subset.

## Output
Save to `./outputs/<YYYY-MM-DD>_icp_<slug>.md`:
```
ICP: firmographics · behaviors · JTBD (functional/emotional/social) · top pains/needs (with impact)
Decision unit & journey
Disqualifiers (who is NOT a fit) · ideal-of-the-ideal subset
GTM implications (targeting + messaging hooks)
```

## Avoid
- An ICP so broad it excludes no one — it should drive focus.
- Demographics with no behavioral or JTBD basis.
