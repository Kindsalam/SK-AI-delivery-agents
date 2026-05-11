# win-loss-synthesis-agent

**Tier:** LT cadence
**Cadence event:** Quarterly win/loss readout, with a monthly interim digest
**Cadence:** Monthly digest on the first business day. Quarterly synthesis in the last week of the quarter.

## What it does

Turns the win/loss programme that exists on paper into an actual deliverable. The head of product stops needing to carve out a Friday once a quarter to assemble it.

## Reads from

- Win/loss interview notes
- CRM closed-won and closed-lost reasons
- Sales-call transcripts where consented
- Competitive intelligence notes
- Product-analytics activation funnels for the win cohort
- Churn-survey responses for the loss cohort

## Produces

**Monthly digest:**
- Top three win patterns
- Top three loss reasons
- Evidence excerpts
- Delta against the rolling quarter

**Quarterly synthesis:**
- Full pattern document
- Recommended product, pricing, positioning, and process changes (recommended, not decided)

Lands in the leadership Confluence space.

## Audience

Head of product, GTM lead, GM, sales leadership, design-partner programme owner.

## Pain it removes

The win/loss programme that only produces a synthesis when the head of product carves out a Friday for it.

## Verdict on dream-team originals

**New.** The dream-team article had no win/loss equivalent.

## Prompt-shape sketch

The prompt tells the runtime to read the win/loss inputs and produce a monthly digest with top patterns, evidence excerpts, and a delta against the rolling quarter. The quarterly synthesis is longer and includes recommended changes per dimension (product, pricing, positioning, process). The recommendations are flagged as recommendations, not decisions. The LT decides.

## Risks and cautions

CRM closed-lost reasons are notoriously thin ("price too high", "went with competitor"). The agent will surface these as primary reasons even when the underlying causes are deeper. Push the GTM team to capture richer loss reasons during sales calls and post-mortems.

If sales-call transcripts are not consented or not transcribed, the synthesis is missing the most useful input. Treat that as a programme-level fix, not an agent-level workaround.

Pattern recognition can find spurious patterns. The first three months of running this agent will teach the LT which patterns the agent is reliable on and which are noise.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
