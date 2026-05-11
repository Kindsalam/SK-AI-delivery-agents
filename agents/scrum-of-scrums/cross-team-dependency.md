# cross-team-dependency-agent

**Tier:** Scrum of Scrums / multi-team coordination
**Cadence event:** Scrum of Scrums (a coordination convention, not a Scrum Guide event. Equivalent in Nexus is the Nexus Daily Scrum, in SAFe the ART Sync)
**Cadence:** Daily, posted 30 minutes before the SoS standup. Also on-demand for ad-hoc dependency reviews.

## What it does

Reads Jira "is blocked by" and "blocks" links across every participating team's board so the SoS does not spend twenty minutes asking each team for a status check. The first ten minutes of SoS become real conversation, not a round-the-table status call.

## Reads from

- Jira dependency links across all participating teams' boards (`is blocked by`, `blocks`)
- Cross-team Epic links
- The shared component ownership matrix in Confluence
- Recent commits to shared repos in GitHub
- Dependency-tagged Slack threads in cross-team channels

## Produces

A dependency one-pager in the SoS channel:
- Dependencies due this week, with status from the owning team
- Dependencies that slipped, with new ETA
- Dependencies newly added in the last 24 hours
- Orphan items: linked but no owning team has it on their sprint

Each line names both teams.

## Audience

RTE or program manager, tech leads from each team, group product manager.

## Pain it removes

The SoS that opens with twenty minutes of cross-team status check.

## Verdict on dream-team originals

**New.** The dream-team article was single-team. Cross-team dependency tracking is a different problem at a different scale.

## Prompt-shape sketch

The prompt tells the runtime to read every participating team's board, follow the dependency links across team boundaries, and group items into the four buckets (due this week, slipped, newly added, orphan). The prompt tells the runtime to name both teams for every dependency and link to the underlying Jira tickets. The agent does not chase the owning teams. It surfaces the shape so the SoS can do that.

## Risks and cautions

This agent is only as good as the dependency hygiene. If teams do not link blockers, the agent will not see them. The first month of running this often surfaces how few dependencies are linked in Jira.

Some teams prefer to track dependencies in a separate doc (Confluence, a spreadsheet, a plan-on-a-page). The agent can read those too, but it is harder. Push the dependency-link discipline first.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
