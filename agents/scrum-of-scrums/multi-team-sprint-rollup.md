# multi-team-sprint-rollup-agent

**Tier:** Scrum of Scrums / multi-team coordination
**Cadence event:** Multi-team showcase / program review
**Cadence:** End of every sprint. Runs the morning after each team's review.

## What it does

Stitches each team's sprint-end signal into a single program-level read so the program manager stops chasing six teams for status. The deck nobody read becomes the email everyone reads.

## Reads from

- Each team's Sprint Goal verdict (hit / partial / missed) from sprint-goal-tracker-agent
- Jira Epic and Initiative progress across teams
- Multi-team OKR progress if held in Jira or a separate tool
- The standup-update output for each team

## Produces

A program-level rollup in the program channel:
- One line per team: Sprint Goal verdict and headline
- One paragraph per Initiative: what moved, what slipped, what is at risk
- A single paragraph at the top summarising what the data says about the sprint just ended (the rollup is a data summary. The program manager interprets)

## Audience

Program manager, RTE, group product manager, engineering managers, the leadership audience for the program.

## Pain it removes

Hand-assembling a rollup deck every fortnight by chasing six teams for status.

## Verdict on dream-team originals

**Make.** The dream-team project-or-product-updates-agent was a single-team agent escalating to leadership. This is the multi-team version. The diff: this one is fed by the team-level agents (sprint-goal-tracker, standup-update) rather than reading raw Jira at program scale. Both shapes can exist, the team-level one is in Tier 1, this one stitches them together.

## Prompt-shape sketch

The prompt tells the runtime to read each team's sprint-end outputs (Sprint Goal verdict, standup-update headline), pull Initiative-level Jira progress that crosses teams, and assemble a rollup with one line per team, one paragraph per Initiative, and a single program-level top paragraph. The prompt tells the runtime to write for a leadership audience, not the dev team. Plain English. No deck-flavoured headers.

## Risks and cautions

If teams do not run sprint-goal-tracker-agent, this agent has no goal-verdict input and will fall back to Jira status, which is noisier. Push teams to commit a Sprint Goal in a known place first.

A rollup is only useful if the leadership audience reads it. Push for the rollup to land where leadership reads (email, Slack channel they use), not where it is convenient for the program manager to write.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
