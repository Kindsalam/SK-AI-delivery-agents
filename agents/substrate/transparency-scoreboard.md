# transparency-scoreboard

> **Status: substrate, not an agent.** Every other item in this repo is a prompt the runtime runs against the right MCP servers on the right cadence. This one is not. It is a dashboard. I am keeping it in the repo because the agents above all point at it, and because the dream-team article named it.

## What it is

A read-only view of your team's real numbers in one place that everyone can see. The same view for the engineer, the product manager, the GM, and the newest grad on the team. The point is to remove the slide-polishing step. Every dashboard tool has filters, exclusion flags, and metric definitions someone with admin rights can change. The polishing layer does not disappear. It moves from the deck to the dashboard definition. The dashboard definition is a smaller surface to audit than a deck per quarter, but it is not zero. Pick someone outside the chain of command to own the metric definitions, and write the definitions down where the team can see them.

## Why it matters

If you run a delivery org you know how often a quarter-end number gets a haircut before it goes upstairs. The scoreboard takes that move off the table.

The same numbers your team uses internally are the numbers your leadership reads externally. You stop building parallel reports.

## What goes on it

The harder question.

**Activity metrics are easy and almost always wrong.** Story points completed, tickets closed, hours logged.

**Outcome metrics are harder and are what matters.** Cycle time. Promise-vs-shipped gap. Customer-felt change. Time from idea to user value. These are the numbers that tell you whether your team is improving.

The scoreboard is the place where your team agrees on those numbers and stops moving the goalposts.

## How the agents in this repo connect

- **pragmatic-brutal-facts-agent** uses the same baseline the scoreboard uses. The flags reference the same numbers leadership sees.
- **team-dora-agent** pins its weekly card to the scoreboard.
- **roadmap-status-agent** uses the same metric definitions.
- **qbr-pack-prep-agent** reads the scoreboard as one of its inputs.

One source of truth, agents that read it, leadership that sees it without filter.

## Setup

Whichever dashboard tool you already have. Tableau, Looker, Metabase, a Notion page with embedded widgets, an Apple Numbers file with auto-refresh if your team is small enough.

The point is not the tool. The point is the discipline.

## Where it lands

A URL anyone in the org can click. Not behind an admin login wall against an audit-trail tool. Not in a deck. Not in an email. A page.

## Verdict on dream-team originals

**Take, recast.** The dream-team article named this as the fourth primary agent. It was never an agent. Recast as substrate.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
