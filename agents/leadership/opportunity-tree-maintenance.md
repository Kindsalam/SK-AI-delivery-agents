# opportunity-tree-maintenance-agent

**Tier:** LT cadence
**Cadence event:** Weekly continuous-discovery review (Teresa Torres discipline)
**Cadence:** Runs Friday afternoon, after the week's discovery interviews are transcribed.

## What it does

Keeps the opportunity-solution tree alive instead of getting built once at the start of the quarter and never touched again.

The opportunity-solution tree is Teresa Torres's continuous-discovery framework. The tree itself is PM-owned. The agent is a draft layer between raw research and the canonical tree. New opportunities are flagged as candidates because the tree is a structured artefact rather than a feedback inbox. The PM and the discovery trio (PM, designer, engineer) decide what becomes an opportunity. Existing opportunities get a frequency count and a recency timestamp. Branches that have not had a new data point in 60 days are flagged for pruning.

## Reads from

- Discovery interview transcripts (Notion has a community MCP server; Dovetail and Otter do not have MCP servers as of mid-2026, so you will need to wrap their public APIs)
- Customer-support ticket categories
- In-product feedback
- NPS verbatims
- Sales-call notes if available
- The current opportunity-solution tree

## Produces

A draft updated opportunity-solution tree:
- New opportunities flagged as candidates, not auto-merged
- Existing opportunities updated with frequency count and recency timestamp
- Branches not touched in 60 days flagged for pruning

Lands as a new version of the tree in the discovery workspace, with a Slack summary of what changed.

## Audience

Head of product, product managers, design researchers.

## Pain it removes

The opportunity tree that gets built once and is never updated, so by week six it lies.

## Verdict on dream-team originals

**New.** None of the dream-team originals touched discovery.

## Prompt-shape sketch

The prompt tells the runtime to read the week's interview transcripts and other discovery inputs, identify new opportunities (candidates only, not merged into the tree), update existing opportunities with frequency and recency, and flag stale branches. The agent does not edit the canonical tree. It produces a draft and a summary. The PM merges or rejects.

## Risks and cautions

Discovery work has a low signal-to-noise ratio. The agent will surface candidates that look like opportunities but are one-off complaints. A human pass before merging is non-negotiable.

If discovery interviews are not transcribed, the agent has nothing to read. Push for transcription discipline first. A week of un-transcribed interviews is a week of lost signal.

The Torres discipline assumes a particular research cadence (continuous, weekly, opportunity-mapped). Teams that do discovery in bursts before launches will need a different shape.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
