# SK-AI-delivery-agents

A starter set of AI agents for delivery teams. Twenty-four of them, plus one substrate (a dashboard, not an agent) and one I deprecated. Each one is a markdown file describing what the agent reads, what it produces, when it runs, who reads it, and a prompt-shape sketch in plain English.

This repo is the companion to my article [Delivery team agents. The full catalog. From standup to the steering committee.](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog). Read the article first if you want the why and the how. Read the files here if you want the what.

## Who this is for

You run a delivery team and you have:

- An AI assistant in your IDE or your terminal (the runtime that thinks)
- Jira and Confluence
- GitHub
- Slack or Microsoft Teams
- Maybe a metrics warehouse, a CI/CD pipeline, a customer-feedback channel
- Maybe MCP servers for some of those, set up once

If you have most of that, you can build any of these agents. The article covers the toolchain in one paragraph.

## How the repo is organised

Three tiers, then a deprecated and a substrate folder.

```
agents/
  team/                  # Tier 1: single team, sprint-aligned
  scrum-of-scrums/       # Tier 2: 2-7 teams aligning
  leadership/            # Tier 3: the LT cadence, quarter-aligned
  also-considered/       # 4 agents I cut from the article. Real, buildable, just not where I would tell you to start.
  deprecated/            # 1 agent I argue against building
  substrate/             # 1 dashboard, not an agent
```

Each agent file has the same shape. Tier, cadence event, cadence frequency, what it reads, what it produces, audience, pain it removes, verdict on the dream-team original if relevant, a prompt-shape sketch in prose, and a risks-and-cautions footer where it matters.

No code. No YAML. No prompt examples to copy and paste. The same logical-level position as the article. The point is to give you the shape so you can build it on your own stack.

## How to use it

1. Pick the agent that buys back the most time on your team. Most teams start with the standup-update-agent because the round-the-room status ritual is the most visible waste.
2. Read the file. Adapt the inputs to whatever your team has. Adapt the audience to whoever you report to.
3. Build it read-only first. Let it post into a channel only your team sees. Watch it for a week. Correct the prompt where it drifts. Fix the data sources where the agent is being lied to by stale tickets.
4. Earn write access later. Only when the team trusts the output do you let it post into wider channels, write back to Jira, or change ticket status.
5. Drop the agents that do not fit. Add the ones I did not name. If you build something good with it, write your own piece.

## Take, make, deprecate

The article names a take / make / deprecate verdict on every agent the dream-team piece named. The short version:

- **standup-update-agent**: take. Spine of the catalog.
- **project-or-product-updates-agent**: make and split. At single-team scale it is the standup-update. At multi-team scale it is the multi-team-sprint-rollup. At LT scale it is the qbr-pack-prep, the qbp-pack-prep, and the portfolio-bets-readout.
- **pragmatic-brutal-facts-agent**: take. Reads drift, not state.
- **transparency-scoreboard**: take, recast as a substrate, not an agent.
- **health-check-agent**: deprecate. Surveillance risk on chat tone and 1-on-1 notes is severe. See `agents/deprecated/health-check.md`.
- **DORA-metrics-agent**: take. Now `team-dora-agent`. Watch for Goodhart drift (deploys get sliced, incidents get reclassified).
- **team-performance-agent**: make, with a footnote. Single-team is covered by brutal-facts and team-dora. Lifted to Tier 2 as `chapter-throughput-agent`, parked in `also-considered/` because it needs more team-level data hygiene than most teams have on day one.
- **retrospective-synthesis-agent**: take, plus a per-sprint sibling (`retro-prep-agent`).
- **risk-radar-agent**: make. Single-team risk earns its keep where there is no PM keeping a RAID register. Lifted to program scope as `program-risk-radar-agent` because cross-team risk is where dependencies and integrations compound.

Reasoning is in each agent file and in the article.

## Read access before write access

One principle. Every agent in this repo starts read-only. Always. The first version reads from your systems and posts a draft into a channel only your team can see. Earn write access later. This is the rule that keeps an early-stage agent from doing damage.

## Licence

MIT. Fork it. Use it. Sell something based on it. Attribute if you want. The point is for delivery teams to stop polishing slides and start using the time on the work.

## Status

This is a reference, not a project. MIT licensed. Fork it, adapt it to your stack, drop the agents that do not fit, build the ones I did not name.

I am not maintaining it as a community repo. Pull requests are not accepted. If you build something good with it, write your own piece. The pattern travels better that way.

The canonical source is the companion article: [Delivery team agents. The full catalog.](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog)

## Standards

Australian English. No em dashes. Plain language. Every claim should trace to a real cadence event and a real audience.
