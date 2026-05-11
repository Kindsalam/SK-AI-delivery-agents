# qbr-pack-prep-agent

**Tier:** LT cadence
**Cadence event:** Quarterly Business Review (QBR). Happens right after the quarter finishes.
**Cadence:** Runs twice a week through the final two weeks of the quarter and the first week after the quarter ends, on-demand the morning of the QBR. (Daily regeneration is more compute and more channel noise than a quarterly artefact justifies.)

## What the LT gets

In the first two weeks after the quarter ends, this agent has been assembling the QBR pack so the head of product is not stuck polishing slides until midnight before the meeting. The LT walks in to the same pack everyone else has already read: north-star trend, OKR scorecard, OKR confidence-trend chart per KR, strategic-bets status, planned-versus-delivered roll-up from Jira Plans, top three wins and three misses with root-cause flags, proposed top-three priorities for next quarter, and open questions for the table.

The team that built the work, the team that ran it, and the team that funded it all see the same data. The conversation goes to root cause and to next-quarter calls, not to whose deck has the latest numbers.

The final call is the LT's. The agent flags root causes. Humans analyse them. The agent surfaces evidence excerpts. Humans interpret. The proposed top-three priorities are candidates for the next-quarter conversation, not commitments.

QBR is Quarterly Business Review, run right after the quarter finishes. What happened, what we learned, what to take into the next QBP. Ends the two weeks of slide polishing across product, delivery, and finance that nobody reads twice.

## Reads from

- The north-star metric warehouse query
- The OKR scorecard sheet
- Jira initiatives at the epic-and-above level
- The Jira Plans (advanced roadmap) planned-versus-delivered view for the just-finished quarter
- Product-analytics funnels
- Customer-feedback channels
- Support-ticket category trends
- Win/loss notes from the just-finished quarter
- Design-partner status notes
- The prior quarter's QBR pack for delta tracking

## Produces

The full standard QBR pack as a single document in the leadership Confluence space, mirrored to a Slack thread. Sections fixed:
- North-star trend with the just-finished quarter's movement
- OKR scorecard with red / amber / green per key result
- OKR confidence-trend chart per key result (the diagnostic that says "we missed because we kept dropping confidence and did nothing", versus "we missed because the world changed in week eight")
- Strategic-bets status per bet (mirrors the portfolio-bets-readout-agent line)
- Planned-versus-delivered roll-up from Jira Plans
- Top three wins with evidence
- Top three misses with a root-cause flag (the analysis is human)
- Proposed top three priorities for next quarter
- Open questions for the executive table

## Audience

Head of product, GM, COO, board members in smaller orgs, steering committee in larger orgs.

## Pain it removes

The polishing economy at quarter-end.

## Verdict on dream-team originals

**New.** The dream-team project-or-product-updates-agent at single-team scale becomes the standup-update. At LT scale it becomes the QBR pack and, separately, the portfolio-bets-readout. Different cadence, different artefact.

## Prompt-shape sketch

The prompt tells the runtime to read the inputs and assemble a standard QBR pack with the fixed sections above. The prompt tells the runtime to flag root causes rather than analyse them, to surface evidence excerpts rather than narratives, and to write open questions for the executive table rather than recommended decisions. The agent prepares. The room decides.

## Risks and cautions

QBR packs become a set piece. The fixed-section structure is intentional. If sections start sliding to fit a particular quarter, the comparison value across quarters is lost. Hold the structure.

The "root-cause flag" line is the most likely to be wrong. The agent points at correlation. Causation needs human judgement. The pack should be explicit that flags are starting points for discussion, not conclusions.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
