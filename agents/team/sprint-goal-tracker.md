# sprint-goal-tracker-agent

**Tier:** Team Scrum cadence
**Scrum event:** Sprint Goal commitment (tracked across the Sprint, surfaces in the Daily Scrum and the Sprint Review)
**Cadence:** Runs daily. Trajectory line lands inside the standup-update-agent's one-pager and posts as a separate short status line.

## What it does

Watches the Sprint Goal so it does not get written at planning and forgotten until review. Produces a one-line trajectory and a one-paragraph projection. Linked to the items at risk.

## Reads from

- The Sprint Goal as written in Jira sprint metadata or Confluence
- The items linked to the goal
- Their status and effort burned
- Days remaining in the sprint

## Produces

- A one-line trajectory: on track, drift on item X, off-goal
- A one-paragraph projection: at current pace the goal lands on day Y, two days late
- The trajectory line also lands inside the standup-update-agent's one-pager

## Audience

Product owner, scrum master, dev team.

## Pain it removes

Sprint Goals that exist on paper and never get checked. The Scrum Guide is most explicit about the Sprint Goal (it is named throughout, alongside the Product Goal and the Definition of Done as one of the three commitments). It is also the commitment teams skip most often in practice.

## Verdict on dream-team originals

**New.** The dream-team article folded Sprint Goal trajectory into the standup-update agent. Splitting it out gives the artefact its own cadence and its own visibility line.

## Prompt-shape sketch

The prompt tells the runtime to read the Sprint Goal text, identify the linked items, compute the burn rate against days remaining, and produce a one-line verdict (on track, drift on item X, off-goal) plus a one-paragraph projection. The prompt tells the runtime to keep the verdict tight enough to fit inside the standup-update one-pager and to flag specific items at risk by name and link.

## Risks and cautions

If the Sprint Goal is not written down anywhere the agent can read, it cannot do this job. Push the team to write the Sprint Goal in the same place every sprint (Jira sprint metadata is the canonical place; a Confluence page works too).

If the items linked to the Sprint Goal are not flagged as such in Jira, the agent cannot tell which items contribute to the goal. Use a label, a fix-version, or a custom field. Pick one and stick to it.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
