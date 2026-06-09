---
name: messaging
description: "Turn positioning and value propositions into audience-specific value-proposition statements for marketing, sales, and onboarding. Use when writing marketing copy, sales messaging, or onboarding messages, or building a messaging house. (Articulation layer; strategy owns the underlying value prop.)"
---
# Messaging

Translates positioning and the core value proposition into compelling, audience-specific statements — the words marketing, sales, and onboarding actually use.

## Inputs
- The positioning and/or existing value proposition(s), and the target segments. Read attached files first; reuse `positioning` and strategy `value-proposition` outputs from `./outputs/`.

## Load company context
Read `./company-context/03-users-personas.md` (segments/pains), `01-product.md`, and `08-voice-tone.md` (brand voice).

## Method
1. Start from the positioning and core value prop; identify the segments/contexts to write for (marketing, sales, onboarding — and key personas within).
2. For each, write a value-proposition statement that: addresses that specific segment/use case, leads with the primary benefit and desired outcome, names the capabilities that make it possible, and uses language that resonates in the brand voice.
3. Add supporting proof points (social proof, metrics) where they sharpen the claim.

## Output
Save to `./outputs/<YYYY-MM-DD>_messaging_<slug>.md`. Per audience/segment:
```
For <segment / context>: <value-prop statement — benefit → how → why us>
Proof points: …
```
Group into a simple messaging house (core message → audience variants).

## Avoid
- Feature lists dressed up as messaging — lead with outcome, not mechanism.
- One generic message for every audience; tailor to the segment's job and context.
