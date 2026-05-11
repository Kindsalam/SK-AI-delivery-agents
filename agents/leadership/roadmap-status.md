# roadmap-status-agent

**Tier:** LT cadence
**Cadence event:** Monthly roadmap refresh
**Cadence:** Weekly digest, monthly deep document.

## What it does

Keeps the roadmap honest with what has happened, not what the product manager remembered to write down before the monthly meeting.

## Reads from

- Jira initiatives at the epic-and-above level
- ProductBoard or Aha or Jira Product Discovery (whichever the org uses)
- Engineering capacity estimates from delivery
- Dependency notes
- Last month's roadmap snapshot for delta

## Produces

- **Weekly:** a drift digest in the product channel covering initiatives that slipped a milestone or had a dependency move (LT does not want a daily ping every time something twitches)
- **Monthly:** a structured roadmap-delta document in the product Confluence space, linked from the public or internal roadmap view. What shifted, why per the data not per opinion, which initiatives are now at risk against their committed quarter, which are running ahead

If you have a Tier 2 program manager, route the daily drift signal to them via cross-team-dependency-agent rather than into the LT channel. The LT reads the weekly digest and the monthly delta. The daily signal belongs at the program tier.

## Audience

Head of product, GMs, design-partner cohort if the roadmap is shared with them.

## Pain it removes

The hand-curated monthly roadmap update that is one sprint behind reality.

## Verdict on dream-team originals

**New.** The dream-team project-or-product-updates-agent flattened roadmap state into a daily update. Roadmap state at LT cadence is its own artefact.

## Prompt-shape sketch

The prompt tells the runtime to compare current Jira initiative state to last month's snapshot and flag deltas: slipped milestones, moved dependencies, scope changes. The daily flag is one line per drift. The monthly document is structured: per initiative, what shifted, why the data says it shifted, what it means for the committed quarter. The agent does not propose roadmap changes. The head of product does that.

## Risks and cautions

Roadmaps drift. The agent will flag every drift. The reader has to filter. If the channel becomes noisy with daily drift flags, the team will mute it. Tune the flag threshold (only flag drifts that affect the committed quarter, not every milestone movement) to keep the channel useful.

If the monthly snapshot is not stored, the agent has nothing to delta against. Pin the monthly snapshot somewhere stable (Confluence page, S3 bucket, repo) so the comparison works.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
