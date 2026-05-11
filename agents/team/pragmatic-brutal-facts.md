# pragmatic-brutal-facts-agent

**Tier:** Team Scrum cadence
**Scrum event:** Daily Scrum (sits beneath the standup-update, posted earlier)
**Cadence:** Daily, posted 06:30-07:00 so it lands before the standup-update.

## What it does

Reads drift, not state. Tells the team what is moving wrong against the team's own baseline. Posts a short flag list, names the trend and the magnitude, does not infer cause and does not propose fix. The team walks into standup unable to pretend they did not see it.

## Reads from

- Jira: cycle time, lead time, sprint scope churn, commitment-vs-delivery delta, story carry-over rate (rolling 60-90 day baseline)
- GitHub: PR review time, PR reopen rate, merge frequency
- The bug tracker: reopen rate, defect age
- Customer escalation queue if one exists

## Produces

A short flag list in the team channel. One sentence per flag. Names the trend and the magnitude. Example: *Cycle time has jumped from 3.2 to 5.8 days over the last seven sprints.* No cause inference. No fix proposal. Three to four flags max on most mornings.

## Audience

Whole dev team, scrum master, engineering lead. Same channel as the standup-update, posted earlier.

## Pain it removes

Retro archaeology. The discovery weeks late that something started breaking five sprints ago.

## Verdict on dream-team originals

**Take.** The dream-team description is the right shape. Single-team agent. Reads drift against the team's own baseline rather than industry benchmark. Tier 1.

## Prompt-shape sketch

The prompt tells the runtime to compare today's metric snapshot to the rolling 60-90 day baseline. The prompt tells the runtime to flag any metric outside one standard deviation, write one sentence per flag, name the trend and the magnitude, link each flag to the underlying data source. The prompt explicitly forbids cause inference and fix proposals. The team will discuss those.

## Risks and cautions

The agent is useless without a baseline. The first job is to compute one. Take the last 60 to 90 days of metrics, take the median per metric, take the standard deviation, treat anything more than a single deviation off as worth flagging. Industry benchmarks will not help. What matters is what is normal for this team, in this product, on this stack, under this leadership.

Gamed metrics will produce gamed flags. If your team is incentivised to game velocity, the agent will flag the symptom, not the cause.

The 60-90 day baseline backfill is real engineering work. Querying changelog across many issues hits Jira Cloud per-tenant rate limits fast. Most teams will need to cache via a side-car process rather than running the baseline computation live each morning. Jira Data Center customers will need to confirm their MCP server flavour supports the Sprint history endpoints. Coverage as of mid-2026 is partial.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
