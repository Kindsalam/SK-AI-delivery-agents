# chapter-throughput-agent

> **Status: also-considered.** Real, buildable, narrow audience. I cut it from the article because the audience (engineering chapter leads, principal engineers, head of engineering at program scale) is narrower than the rest of Tier 2, and because it needs the most existing data hygiene of any Tier 2 agent. Build it if you have a chapter or guild structure already running and team-level DORA data already flowing.

**Tier:** Scrum of Scrums / multi-team coordination
**Cadence event:** Chapter or guild cadence (engineering chapter, design chapter), SoS-adjacent
**Cadence:** Weekly.

## What it does

Surfaces the chapter's own pattern across teams. Where the chapter as a whole is healthy, where one team is dragging the average, what cross-team patterns are showing.

## Reads from

- Per-team DORA metrics (from team-dora-agent on each team)
- Throughput and predictability per team (Jira)
- Engineering health signals if the team-performance pattern is in place

## Produces

A chapter-level read pinned to the chapter Confluence page:
- Where the chapter is healthy
- Where one team is dragging the average
- Cross-team patterns showing (every team has the same review-time creep, or one team has a different shape entirely)

## Audience

Engineering manager, principal engineer, head of engineering at the program level, chapter lead.

## Pain it removes

Engineering leads who manage by anecdote because no one has time to compare team-level data.

## Verdict on dream-team originals

**Make.** The dream-team team-performance-agent was the single-team version. That role at single-team scale is largely covered by pragmatic-brutal-facts and team-dora. The remaining gap is comparative performance across teams. This is the chapter version.

## Prompt-shape sketch

The prompt tells the runtime to read each team's DORA card and Jira throughput / predictability metrics, identify outliers (one team dragging on review time, one team running a different deployment frequency), and surface cross-team patterns. The agent does not propose interventions. The chapter lead does.

## Risks and cautions

Comparative performance between teams is sensitive. A weekly post saying "Team B is dragging the chapter on cycle time" can land badly even when it is true. The chapter lead should hold the read and decide how to use it.

Different teams have different work shapes. A platform team and a customer-facing team will not have the same DORA profile. The agent's outlier detection has to be tuned for that or it will produce useless flags.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
