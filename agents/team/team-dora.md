# team-dora-agent

**Tier:** Team Scrum cadence
**Scrum event:** Cross-cutting (sits under all events, surfaces in retro and review)
**Cadence:** Updated daily, summarised weekly.

## What it does

The four-numbers card. Deployment frequency, lead time for changes, change failure rate, mean time to recovery. Trend arrow per metric. No commentary. The smallest set of numbers Google's research says predict performance.

## Reads from

- CI/CD pipeline: deployment frequency, build success, production deploy timestamps
- Incident management tool: MTTR, change-failure rate
- GitHub joined to the CI/CD pipeline: lead time for changes (computed from the first commit on a PR through to the production deploy timestamp. You need both inputs because GitHub alone does not know when something hit production)

## Produces

A weekly DORA card in the team channel and pinned to the transparency scoreboard:
- Deployment frequency
- Lead time for changes
- Change failure rate
- Mean time to recovery

Trend arrow per metric. No commentary. The numbers speak.

## Audience

Engineering lead, dev team, scrum master. Visible to leadership through the scoreboard.

## Pain it removes

Engineering improvement debates that run on opinion.

## Verdict on dream-team originals

**Take.** The dream-team DORA-metrics-agent shape is right. The Accelerate research (Forsgren, Humble, Kim) is solid. The work was acquired by Google in 2018. The metrics are unambiguous. They sit on the transparency scoreboard.

## Prompt-shape sketch

The prompt tells the runtime to read the four DORA inputs from the CI/CD pipeline, the incident tool, and GitHub, and produce a card with each metric, this week's value, and a trend arrow against the rolling 4-week average. The prompt explicitly forbids commentary. The card is for the team and the scoreboard. Discussion happens in retro and review.

## Risks and cautions

If your incident management is informal (people post in Slack, no tracker), MTTR and change-failure rate will be wrong. Tighten incident tracking before relying on those two metrics.

DORA is performance-correlated, not improvement-causing. Wiring up the agent does not make the team faster. The card creates a conversation. The team makes the team faster.

Watch for Goodhart drift inside the first quarter. Once you measure against DORA, deployment frequency tends to rise because deploys get sliced into smaller pieces. Change-failure rate tends to fall because incidents get reclassified as "non-deploy-related". The agent will not catch this. The engineering lead has to.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
