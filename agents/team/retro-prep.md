# retro-prep-agent

**Tier:** Team Scrum cadence
**Scrum event:** Sprint Retrospective
**Cadence:** Runs the morning of the retro.

## What the team gets

Before the retro, this agent has already done the data work and drafted candidate actions for the team to react to. The team walks in to a Confluence page with:

- The numbers from this sprint laid out (cycle time delta, scope churn, Sprint Goal verdict)
- The prior retro's actions tracked for completion (which moved, which got promised again and forgotten)
- Three candidate themes drawn from the brutal-facts patterns and labelled with their recurrence count (*"this is the third retro discussing PR review time"*)
- A draft candidate action for each theme: concrete next steps in the team's typical action-item style, with a proposed owner and a check-in date

The team accepts, edits, or rejects each draft action. The hour goes to deciding what to try next, not to reconstructing what happened or fishing for a new idea when last retro's idea did not work.

What the team stops doing: opening the retro cold and spending the first ten minutes trying to remember what happened. Re-treading the same three themes because nobody can think of a different action to try. The "we'll think about it" non-action that the team agrees to and then forgets.

The final call is always the team's. The candidate actions are starting points. The team owns the conversation and owns what it commits to try.

## Reads from

- Last sprint's standup-update-agent posts
- Last sprint's pragmatic-brutal-facts-agent flags
- Last sprint's review outcome (Sprint Goal hit / partial / missed)
- Jira metrics for the sprint just ended (cycle time, scope churn, carry-over)
- The previous retro's action items and their completion status
- The history of retro action items across the last quarter (which patterns recur, which fixes worked, which did not, which themes the team has discussed three times without resolution)
- The team's agreed retrospective format (Start/Stop/Continue, 4Ls, Glad/Sad/Mad, etc.) so the candidate themes and actions land in the format the scrum master uses
- The team's retro board on Miro or FigJam if that is where the team runs them

## Produces

A retro starter pack pinned to the Confluence retro page. Sections:

### 1. What the data says happened this sprint

Numbers, no narrative:

- Cycle time delta vs the rolling baseline
- Scope churn percentage
- Carry-over count
- Sprint Goal verdict
- DORA card snapshot

### 2. Prior retro actions and which moved

Each action item from the previous retro, with status:

- Done
- Started, in progress
- Promised, not started
- Forgotten / dropped

### 3. Three candidate themes for discussion

Each theme:

- Recurrence count (*"this is the third retro discussing PR review time"*)
- One-paragraph framing drawn from the brutal-facts patterns and the standup-update conversation history
- Why it is worth the team's time

### 4. A draft candidate action per theme

Each candidate action:

- **What to try.** Concrete enough that the team can either commit or sharpen it
- **Who would own it.** Proposed owner, in the team's voice (not a generic "the team will...")
- **What success looks like.** A signal the team can check at next retro
- **When to check.** A date or a sprint number

Marked clearly as `[draft, team to confirm/edit/reject]`.

The agent does not write the retro outcome. The team writes that.

## Conventions the agent follows

- **Draft actions land in Confluence**, not in Jira. Jira items for actions get created after the retro, by the action's owner, when the team has confirmed the wording.
- **Every draft action is labelled `[draft, team to confirm/edit/reject]`** so the team is not put in the position of disagreeing with a "decision".
- **Recurrence count is honest.** If a theme has been discussed three times without resolution, the agent says so.
- **Format follows the scrum master's retro ritual.** Start/Stop/Continue if that is the team's format. The agent does not impose a format the team does not use.

## Audience

Whole team, scrum master facilitating.

## Pain it removes

Retros that start cold, retread the same three issues, never check whether last retro's actions got done, and end with an action the team forgets within a week. The team that walks in to a starter pack with the numbers, the prior actions tracked, and three concrete things to argue about gets to spend the hour deciding what to try next. The action items leave the room with owners and check-in dates because the agent put them there as drafts and the team sharpened them.

## Verdict on dream-team originals

**Make.** The dream-team original was a longitudinal synthesiser (now `retro-synthesis-agent`, which still exists). This is the per-sprint sibling. Different cadence (every sprint vs quarterly), different output (starter pack with candidate actions vs cross-sprint pattern doc), different audience (team in the retro vs scrum master and EM). Both belong.

## Prompt-shape sketch

The prompt tells the runtime to read the data sources, identify themes that recur or land hard this sprint, and draft a candidate action per theme that fits the team's typical action-item style. The prompt tells the runtime to be honest about recurrence count and about which prior actions moved versus which got forgotten. The prompt explicitly forbids the agent from writing the retro outcome, naming actions the team has not had a chance to discuss, or assigning Jira items. The candidate actions are starting points. The team commits.

## Risks and cautions

**Run shadow mode for the first week.** The agent drafts in plain text and posts to a channel. The scrum master copies what they want into the Confluence retro page. After a week of trust, enable Confluence write access where the agent updates the retro page directly.

**The team can become passive.** If the agent's draft becomes the agenda, the team stops surfacing what it feels and just reacts to what the agent put on the page. The scrum master has to hold the line: agent drafts are starting points, the team owns the conversation. When the team finds a fourth theme the agent missed, that is the retro working as it should.

**Candidate actions can be too clean.** The agent might propose generic actions that don't fit the team's context. Trust the team to redirect. *"That action assumes a thing that is not true here"* is a perfectly good response to an agent's draft.

**The agent's pattern recognition is only as good as the retro history.** New teams won't have enough. Three or four retros worth of action-item history is the minimum before recurrence-counting is meaningful.

**Recurrence counts can land badly.** *"This is the third retro discussing PR review time"* is honest, but it can read as an indictment. The scrum master should hold the recurrence framing and decide how to introduce it. Posted blindly to a public channel, it can land poorly.

**The agent does not edit existing actions.** Editing actions the team has already shaped carries context the agent does not have. The agent only drafts new candidate actions per theme.

---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
