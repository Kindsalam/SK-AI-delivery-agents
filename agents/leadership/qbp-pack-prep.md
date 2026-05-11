# qbp-pack-prep-agent

**Tier:** LT cadence
**Cadence event:** Quarterly Business Planning (QBP). The forward-looking half of the quarter.
**Cadence:** Runs in the first week of the new quarter, on-demand the morning of QBP.

## What the LT gets

In the first week of the new quarter, this agent has already done the QBP pack assembly. The leadership table walks into planning with proposed objectives drawn from the prior quarter's QBR, candidate key results per objective with evidence and rationale, the OKR carry-over decision per KR (which survive, which die, which mutate), the strategic-bets register snapshot at quarter-start, capacity allocation by bet, a hypothesis-evidence-spend line per bet, and the top three open strategic questions for the planning room.

The LT picks the objectives, sharpens the KRs, and decides the bets. The agent has done the assembly so the room can spend its time on the actual decisions, not on whose deck has the latest numbers.

The final call is the LT's. The agent does not pick objectives, sets no commitments, and never updates the OKR sheet, the bets register, or the capacity allocation directly. The PM (or whoever the LT delegates) updates the canonical artefacts after the planning meeting.

QBP is the planning half: what we will commit to next, why, and against which evidence.

A note on terminology. Many orgs run a single end-of-quarter QBR that does both review and forward-look in one event. Splitting the artefacts into QBR (this agent's sibling) and QBP is a deliberate pedagogy: the planning half and the review half need different inputs and ship at different points in the cycle. If your org runs one combined event, run both agents and stitch the output. The artefacts being two does not require the meetings to be two.

## Reads from

- The QBR pack from the just-completed quarter (qbr-pack-prep-agent output)
- The strategic-bets register
- The OKR scorecard from the just-completed quarter
- The opportunity-tree from opportunity-tree-maintenance-agent
- Win/loss themes for the last quarter
- Capacity forecasts from delivery
- Market intelligence and competitive notes if the team keeps them

## Produces

A QBP pack in the leadership Confluence space:
- Proposed objectives for next quarter
- Candidate key results per objective with evidence and rationale
- The OKR carry-over decision per key result from the previous quarter (which survive, which die, which mutate)
- The strategic-bets register snapshot at quarter-start
- Capacity allocation by strategic bet
- Hypothesis-evidence-spend line per bet
- Top three open strategic questions for the planning room

The agent does not pick the objectives. It assembles the candidates so the leadership table can.

To make the hypothesis-evidence-spend line concrete: *Hypothesis: the AU mid-market wants the cyber feature. Evidence: 6 of 8 design-partner conversations confirmed, 2 are uncertain, 1 product-analytics signal supports. Spend: 2 engineers and a PM for 6 weeks.* One line per bet. The leadership table reads what we are betting on, what the data says so far, and what it is costing.

## Audience

Head of product, GM, COO, steering committee, function leads attending the planning.

## Pain it removes

The new quarter starting from a blank slide deck or from last quarter's unmoved objectives renamed.

## Verdict on dream-team originals

**New.** The dream-team article was sprint-cadence. QBP is its own beast.

## Prompt-shape sketch

The prompt tells the runtime to read the QBR output, the strategic-bets register, the OKR scorecard, the opportunity-tree, and the win/loss themes from the just-completed quarter, and assemble a planning pack with proposed objectives, candidate key results, capacity allocation, and hypothesis-evidence-spend per bet. The prompt explicitly forbids the agent from picking the final objectives. The pack is candidates, not commitments.

## Risks and cautions

If the QBR pack was thin or skipped, the QBP pack has weaker inputs and the proposed objectives will read as fresh rather than continuous with what the team learned last quarter. Push for QBR completion before QBP.

Strategic bets are human bets. The agent's hypothesis-evidence-spend line is a prompt for human judgement, not a recommendation to execute. Make sure the pack is read in a room where the LT can disagree with the agent.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
