# okr-checkin-agent

**Tier:** LT cadence
**Cadence event:** Weekly OKR check-in (Christina Wodtke shape: Monday commitments, Friday wins)
**Cadence:** Runs Monday 7am and Friday 4pm team-time.

## What it does

Runs the weekly OKR check-in (Christina Wodtke's discipline, adapted to a Monday-commitment / Friday-win split) so the OKR sheet is not opened only the day before the meeting and the confidence ratings are not guessed in the room. The confidence rating per key result is the part that matters. The trend across weeks tells you whether you will hit the quarter. That is the load-bearing output, not the Monday/Friday split.

## Reads from

- The OKR sheet (a sheet, Confluence, Lattice, Ally.io, WorkBoard, Mooncamp). OKRs do not live in Jira Product Discovery, which is for opportunity / idea management
- Product-analytics events tied to each key result
- Jira initiative progress
- Last week's check-in notes for delta

## Produces

Two short documents per week.

**Monday post:**
- Which key results moved last week
- Which did not
- What the team committed to this week

**Friday post:**
- Which commitments shipped
- Which slipped
- Confidence rating per key result for the rest of the quarter, plotted against last week's number. The trend is the signal.

Lands in the product-leadership Slack channel and is appended to the OKR sheet as a comment row.

## Audience

Head of product, product managers running each objective, GM as a read-only audience.

## Pain it removes

OKRs that get treated as a quarterly artefact instead of a weekly discipline.

## Verdict on dream-team originals

**New.** The dream-team article had no leadership-cadence equivalent.

## Prompt-shape sketch

The prompt tells the runtime to read the OKR sheet, the analytics events tied to each key result, and the Jira initiative progress, and produce two compact posts per week. Monday post is short and forward-looking (commitments). Friday post is short and backward-looking (wins, slips, confidence). Confidence is a number with a one-line reason, not a feeling. The agent does not adjust the OKR sheet itself.

## Risks and cautions

Confidence ratings can drift toward optimism if PMs feel pressure to "look good". The agent reads the data, but the data only goes so far. Leadership has to model honest confidence ratings or the agent's prompt becomes theatre.

If the OKR sheet has more than one source of truth (one in Notion, one in Jira, one in a Confluence page that nobody updates), the agent will pick one and the others will diverge. Pick one canonical source first.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
