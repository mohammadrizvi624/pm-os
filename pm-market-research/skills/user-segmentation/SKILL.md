---
name: user-segmentation
description: "Segment your existing users from feedback/usage data by behavior, JTBD, and needs (bottom-up, ≥3 segments). Use when clustering the user base from real data to guide product strategy. For top-down market segments, use market-segmentation."
---
# User segmentation

Surfaces behavioral, needs-based clusters in your *actual* user base from feedback and usage data — bottom-up, behavior over demographics.

## Inputs
- The user data (feedback, interviews, support tickets, usage logs, surveys). Read attached files first.

## Load company context
Read `./company-context/03-users-personas.md` and `01-product.md`.

## Method
1. Organize the user data; extract behavioral patterns, usage modes, and journeys.
2. Map JTBD, motivations, and unmet needs per user.
3. Cluster into ≥3 distinct, coherent, non-overlapping segments by behavior + needs similarity.
4. Characterize each with representative quotes; assess product fit and churn risk.
5. Prioritize: invest / maintain / de-prioritize, weighing growth and revenue potential vs effort to serve.

## Output
Save to `./outputs/<YYYY-MM-DD>_user-segments_<slug>.md`. Per segment (≥3):
```
Segment: <name>  | Size/%: …  | One-line characterization
Behavior: <use cases, frequency, sophistication, integrations>
JTBD & motivations: …  | Key needs/pains: …  | Workarounds: …
Product fit: <what they value / what frustrates / churn risk>
Differentiated value: <what could be unlocked>
Priority: invest / maintain / de-prioritize — why
```

## Avoid
- Segmenting on demographics alone — anchor on behavior and JTBD.
- Segments that aren't distinct or actionable; flag any under-represented in the data.
