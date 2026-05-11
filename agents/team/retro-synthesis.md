# retro-synthesis-agent

**Tier:** Team Scrum cadence (longitudinal, not per-sprint)
**Scrum event:** Sprint Retrospective (across a quarter, not a single one)
**Cadence:** Runs at the end of every sprint as a partial pass, full pass quarterly.

## What it does

Reads every retro across a quarter and tells the team whether they are fixing what they keep complaining about. Surfaces the patterns the team is too close to see: themes that keep coming up sprint after sprint and never close, themes that surfaced and were genuinely fixed.

## Reads from

- Every retro's notes, action items, and themes for the last 4-12 sprints (Confluence retro pages or whichever retro tool the team uses)

## Produces

A quarterly synthesis in Confluence:
- Themes that keep coming up sprint after sprint and never close
- Themes that surfaced and were genuinely fixed
- A short paragraph per recurring theme summarising what the team has tried and what has not worked

## Audience

Scrum master, engineering lead, product owner, sometimes the EM above the team.

## Pain it removes

The team promising to fix the same three things every quarter and nobody noticing the pattern.

## Verdict on dream-team originals

**Take.** The dream-team named retrospective-synthesis-agent and the description holds. Added a separate retro-prep-agent for the per-sprint version because the prep job and the synthesis job are different cadences and different outputs.

## Prompt-shape sketch

The prompt tells the runtime to read every retro page from the last 4 to 12 sprints, cluster themes that recur across multiple retros, and check the action-item completion record for each theme. The prompt tells the runtime to write a short paragraph per recurring theme covering what the team has tried, what worked, and what did not. The agent does not propose new actions. The synthesis is for the team to read and decide what to do.

## Risks and cautions

If retros are written inconsistently or in different places, the agent will miss themes. Push the team to land retros in one canonical place before relying on this synthesis.

The synthesis can read as an indictment if the team is sensitive about repeated patterns. The scrum master should hold the synthesis and decide how to use it. Posted blindly to a public channel, it can land poorly.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
