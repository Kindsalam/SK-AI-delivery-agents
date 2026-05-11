# sprint-planning-prep-agent

**Tier:** Team Scrum cadence
**Scrum event:** Sprint Planning
**Cadence:** Runs the morning of Sprint Planning, with a draft 24 hours before so the PO can edit before the room walks in.

## What the team gets

Before Sprint Planning, this agent has already done the goal drafting and the capacity maths. The product owner walks in with two or three draft Sprint Goal candidates already shaped, each tied to specific items in the refined backlog, each with a one-line rationale on the page (*this goal because the Initiative's top metric is X and these items move it*). The PO picks one, sharpens it, or asks for a different one. The team commits to it in the room.

What the team stops doing: reconstructing capacity from leave calendars and on-call rosters under time pressure. Writing goal options under the clock. Picking the easiest goal because the harder goal is half a sentence on a whiteboard with thirty seconds left to discuss it.

The final call is always the team's. The agent drafts. The PO sharpens. The team commits.

## Reads from

- Jira: team velocity over a rolling window the team agreed on (six sprints is a common default. The Scrum Guide does not name velocity at all)
- This sprint's planned capacity: leave calendars, on-call roster, scheduled meetings (the planned-capacity reality)
- The refined and DoR-clean backlog from refinement-prep-agent
- Last sprint's carry-over items
- The parent Initiative's current state and its top metric for the quarter
- The previous sprint's Sprint Goal and verdict (hit / partial / missed) for context
- The team's pattern of Sprint Goals across the last six sprints (so the drafts read in the team's voice, not in a generic Scrum-Guide voice)
- Product-analytics signals tied to the active Epics
- Open customer escalations the team owns

## Produces

Three outputs.

### 1. Two or three draft Sprint Goal candidates

Land in the Confluence Sprint Planning page. Each one:

- A paragraph in the team's voice
- Tied to specific items in the refined backlog (with links)
- One-line rationale: why this goal, what metric it moves, what the team learns if they hit it

### 2. A draft Sprint Backlog per candidate goal

For each candidate goal, the agent shows:

- Which items support that goal
- Capacity-check verdict: does this set fit the realistic capacity? Yes / no / tight
- Items needed but not yet refined (run refinement-prep-agent first if the gap is large)
- Items DoR-clean and ready
- Risks the team is carrying into this sprint from last

### 3. The original planning briefing

In the team channel:

- Realistic capacity for this sprint (in points and person-days)
- Backlog candidates ranked by PO priority and DoR-readiness
- Sprint-goal candidate framing as paragraphs the team can react to
- Risks carried over from last sprint

## Conventions the agent follows

- **Draft Sprint Goal candidates land in Confluence**, not in Jira sprint metadata. Jira sprint metadata gets updated only after the team commits in the room.
- **Each candidate goal is labelled `[agent-drafted, PO to review]`** so the PO knows which paragraph they own and which the team will see in their voice.
- **Capacity numbers are realistic, not aspirational.** Velocity-adjusted for leave, on-call, and scheduled meetings. The agent does not optimise the capacity to match the goal.
- **No commitment.** The agent never sets a Sprint Goal in Jira sprint metadata. That happens after Sprint Planning, when the team commits.

## Audience

- **Primary:** product owner. Reviews the candidate goals before the room walks in.
- **Secondary:** tech lead. Sanity-checks the capacity assumptions.
- **Final:** dev team. Picks the goal they will commit to.

## Pain it removes

The PO drafting goal candidates under time pressure on the morning of planning, frequently picking the easiest rather than the highest-value. The two-hour planning session where the first ninety minutes go to capacity arithmetic and point arguments. The Sprint Goal that gets written by whoever has the most energy left at minute 110 of a two-hour meeting.

## Verdict on dream-team originals

**New.** The dream-team article skipped planning entirely. In my experience, Planning is the second-highest-leverage event after the Daily Scrum, and it deserved its own prep agent.

## Prompt-shape sketch

The prompt tells the runtime to read the Initiative's current top metric, the refined backlog, the team's velocity-adjusted capacity, and the team's recent Sprint Goal patterns. The prompt tells the runtime to draft two or three Sprint Goal candidates, each tied to specific backlog items, each with a one-line rationale, each capacity-checked. The prompt tells the runtime to write the goals in the team's voice (not in a generic Scrum voice) by referencing the recent Sprint Goal patterns. The prompt explicitly forbids the agent from picking a single goal, committing to Jira sprint metadata, or optimising capacity to match the goal. Every draft is candidates and capacity reality. The team picks.

## Risks and cautions

**Run shadow mode for the first week.** The agent drafts in plain text and posts to a channel. The PO writes the actual Confluence page. After a week of trust, enable Confluence write access where the agent updates the planning page directly. The agent never gets Jira sprint-metadata write access. That gate is permanent.

**Velocity-adjusted capacity is a starting frame, not a commitment.** Teams that treat the agent's capacity number as a target will commit to it and the agent will get blamed when they overrun. Treat it as the opening number for a human conversation.

**If the backlog is full of unrefined items, the agent's "ready" list will be tiny and the team will be tempted to commit to unrefined items anyway.** Run refinement-prep-agent first.

**The agent's goal candidates can read clean but miss the team's actual judgement.** If the team has just shipped a hard quarter and the right goal is "stabilise what we've built", the agent might draft a "ship the next big thing" goal because the Initiative pushes that direction. The PO sees what the agent does not. Trust the PO to override.

**Without a clear parent Initiative, the agent's goal-to-metric rationale is hand-waving.** If your org does not have Initiatives with metrics attached, that is the upstream fix to do before this agent earns its keep.

---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
