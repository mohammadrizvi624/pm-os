---
name: release-notes
description: "Turn tickets, PRDs, or changelogs into clear, user-facing release notes organized by category, leading with the user benefit. Use when writing release notes, a changelog, or announcing what shipped. (Delivery changelog — for launch campaigns/messaging use the GTM/marketing plugins.)"
---
# Release notes

Transforms technical change records into polished, user-facing notes that lead with benefit, not implementation — the delivery changelog, distinct from a launch campaign.

## Inputs
- The raw material (Jira/Linear export, PRD, git log, internal changelog). Read attached files first.

## Load company context
Read `./company-context/01-product.md` and `08-voice-tone.md` (match the product's voice).

## Method
1. Extract per change: what changed, who it affects, why it matters (the benefit).
2. Categorize: New features · Improvements · Bug fixes · Breaking changes (action required) · Deprecations.
3. Write each entry leading with the user benefit, in plain language — no jargon, codenames, or ticket numbers; 1-3 sentences. (e.g. "Dashboards now load up to 3× faster" — not "implemented Redis caching".)
4. Match tone to audience (professional B2B / friendly consumer / developer-focused for APIs).

## Output
Save to `./outputs/<YYYY-MM-DD>_release-notes_<version>.md`:
```
# <Product> — <version / date>
## Highlights — <1-2 sentences on the most impactful change>
## New features — **<name>**: <what it does + why it matters>
## Improvements — **<area>**: <what got better>
## Bug fixes — Fixed <issue in user terms>
## Breaking changes (if any) — **Action required**: <what to do>
## Coming soon (optional) — <teaser for the next release>
```
Offer to format for the channel — blog post, in-app, email, or Slack announcement.

## Avoid
- Technical framing, internal codenames, ticket IDs.
- Burying breaking changes — call out required user action clearly.
