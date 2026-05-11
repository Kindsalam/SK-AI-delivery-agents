# sprint-review-prep-agent

> **Status: also-considered.** This agent is real and buildable. I cut it from the article because the Sprint Review is the event most teams already do reasonably well. There is a stakeholder watching, so the leverage of a prep agent is lower than refinement-prep, planning-prep, or retro-prep. Build it if you have headroom after the Tier 1 keepers.

**Tier:** Team Scrum cadence
**Scrum event:** Sprint Review (Showcase)
**Cadence:** Runs the morning of the Review, also a draft 24 hours before so the team can edit.

## What it does

Assembles the review pack. The PO stops scrambling on the morning to remember what shipped. Stakeholders walk in already knowing what they will see.

## Reads from

- Jira items moved to Done in the active sprint
- Their Acceptance Criteria
- Linked PRs and commits
- Demo-ready flag if the team uses one
- The original Sprint Goal
- Customer-facing release notes if any

## Produces

A draft review pack in Confluence:
- Sprint Goal vs what shipped (one-line verdict)
- Demo agenda in priority order
- Items shipped that do not need a demo
- Items not shipped, with one-line reason
- Questions the team expects stakeholders to ask

Every line links to its ticket.

## Audience

Product owner, dev team presenting, scrum master, business stakeholders attending the review.

## Pain it removes

The PO scrambling on the morning of the Review to assemble what shipped.

## Verdict on dream-team originals

**New.**

## Prompt-shape sketch

The prompt tells the runtime to read the items moved to Done, group them by demo-readiness and Sprint Goal alignment, and assemble a draft review pack. The PO edits, the team rehearses. The agent does not run the review. It sets up the room.

## Risks and cautions

The team can lean on the agent's draft and stop preparing the demo. The prep agent assembles the pack. The team still needs to rehearse the demo and decide who shows what.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
