---
name: lifecycle-marketing
description: "Design lifecycle marketing campaigns — onboarding, activation, retention, re-engagement, and key change comms (e.g. a pricing change) — mapped to the customer lifecycle. Use when building lifecycle/CRM flows, improving activation or retention through messaging, or communicating a change to users. (Runs the campaigns; analytics measures the retention.)"
---
# Lifecycle marketing

Designs the messaging that moves users through the lifecycle — welcome → activation → habit → retention → win-back — and handles sensitive change comms. The campaign side of retention; analytics' `cohort`/retention measures whether it works.

## Inputs
- The lifecycle stage(s) to address and the goal (activate, retain, re-engage, communicate a change). Read attached files first; reuse funnel/cohort findings from `./outputs/` to target the leak.

## Load company context
Read `./company-context/03-users-personas.md`, `01-product.md`, `05-metrics-goals.md` (activation/retention metrics), `08-voice-tone.md`.

## Method
1. Map the relevant lifecycle stage(s) and the behavior to drive at each (the aha/activation moment, the habit, the churn risk).
2. For each, design the campaign: trigger (behavioral/time-based), channel (email/in-app/push), message (in brand voice, leading with user value), and the success metric.
3. Sequence into flows (e.g. an onboarding series with entry/exit criteria) and define suppression/frequency rules so users aren't over-messaged.
4. For a change comm (e.g. pricing): lead with the user benefit/why, give clear notice and any action required, and segment by who's affected.

## Output
Save to `./outputs/<YYYY-MM-DD>_lifecycle_<slug>.md`:
```
| Stage | Trigger | Channel | Message (value-led) | Success metric |
Flows (with entry/exit + frequency rules)
Change comms (if any): who's affected · benefit framing · action required · timing
```

## Avoid
- Over-messaging — set frequency/suppression rules.
- Generic blasts; trigger on behavior and segment by lifecycle stage.
