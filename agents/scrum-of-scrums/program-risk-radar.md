# program-risk-radar-agent

**Tier:** Scrum of Scrums / multi-team coordination
**Cadence event:** SoS program-level risk review
**Cadence:** Daily summary, weekly deep pass.

## What it does

Lifts risk to where risk compounds: across teams, dependencies, integrations, milestones. RAID-style. Surfaces new risks since yesterday, risks whose probability or impact moved, risks closed because the underlying issue resolved, top three risks the program leadership should know today.

## Reads from

- Every team's RAID log (and prompts them to start one if they do not have one)
- Jira items flagged at risk across teams
- The cross-team-dependency-agent output for slipping dependencies
- The integration-readiness-agent output for at-risk integrations
- Customer escalations tagged to a program initiative
- Deadlines and milestone dates from the program plan

## Produces

A risk register update in the SoS channel:
- New risks since yesterday
- Risks whose probability or impact moved
- Risks closed because the underlying issue resolved
- Top three risks the program leadership should know today

RAID-style format. Plain English.

## Audience

RTE, program manager, group product manager, sometimes the portfolio level above.

## Pain it removes

Risks raised in a team retro that never travel up. Risks that travel up too late to do anything about.

## Verdict on dream-team originals

**Make.** The dream-team risk-radar-agent was single-team. Risk is RAID-discipline (probability-impact scoring, mitigation owners, residual risk after mitigation), which the brutal-facts agent does not cover. A single-team risk-radar still earns its keep where there is no PM keeping a register. Lifted to program level here because risks compound across teams: dependencies, integrations, milestones across multiple teams stack up faster than any single-team agent can read.

## Prompt-shape sketch

The prompt tells the runtime to read every team's RAID log, the dependency-agent output, the integration-readiness output, and any customer escalations tagged to program initiatives. The prompt tells the runtime to compute deltas (new risks, moved risks, closed risks) and pick the top three for leadership attention based on combined probability and impact. The prompt explicitly asks for plain English risk descriptions, not consultancy-speak. The agent does not propose mitigations. The program manager and the team owners do that.

## Risks and cautions

If teams do not keep RAID logs, this agent has thin input. It will still surface what it can from Jira and dependency / integration feeds, but the picture will be incomplete. Push teams to keep a RAID log even if it is just a Confluence page.

"Top three" is a forcing function. Some sprints will have eight live risks. The agent has to pick three. It can be wrong about which three matter most. Human review the picks before they go upstream.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
