# qbp-pack-prep-agent

**Tier:** LT cadence
**Cadence event:** Quarterly Business Planning (QBP). Happens before the next quarter starts.
**Cadence:** Runs in the final two weeks of the current quarter, on-demand the morning of QBP. The meeting itself happens before the next quarter begins.

## What the LT gets

In the final two weeks of the current quarter, this agent has been assembling the QBP pack so the leadership table walks into planning with the work already done. The LT sees proposed objectives drawn from the current quarter's running actuals, candidate key results per objective with evidence and rationale, the OKR carry-over decision per KR (which survive, which die, which mutate), the strategic-bets register snapshot at quarter-start, capacity allocation by bet drawn from Jira Plans, a hypothesis-evidence-spend line per bet, and the top three open strategic questions for the planning room.

The LT picks the objectives, sharpens the KRs, and decides the bets. The agent has done the assembly so the room can spend its time on the actual decisions, not on whose deck has the latest numbers.

The final call is the LT's. The agent does not pick objectives, sets no commitments, and never updates the OKR sheet, the bets register, or the capacity allocation directly. The PM (or whoever the LT delegates) updates the canonical artefacts after the planning meeting.

QBP is Quarterly Business Planning, run before the next quarter starts. What we will commit to next, why, and against which evidence.

A note on terminology. Many orgs run a single end-of-quarter QBR that does both review and forward-look in one event. Splitting the artefacts into QBR (this agent's sibling) and QBP is a deliberate pedagogy: the planning half and the review half need different inputs and ship at different points in the cycle. If your org runs one combined event, run both agents and stitch the output. The artefacts being two does not require the meetings to be two.

## Reads from

- The current quarter's running actuals: north-star metric, OKR scorecard, strategic-bets progress
- The strategic-bets register
- The OKR scorecard from the current quarter, including a carry-over view of which key results survive, which die, which mutate
- Jira Plans (advanced roadmap) for cross-team capacity forecasts and in-flight initiative state
- The opportunity-tree from opportunity-tree-maintenance-agent
- Win/loss themes from the current and prior quarter
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

The prompt tells the runtime to read the current quarter's running actuals, the strategic-bets register, the OKR scorecard, Jira Plans for capacity, the opportunity-tree, and the win/loss themes, and assemble a planning pack with proposed objectives, candidate key results, capacity allocation, and hypothesis-evidence-spend per bet. The prompt explicitly forbids the agent from picking the final objectives. The pack is candidates, not commitments.

## Risks and cautions

QBP runs on the current quarter's running actuals, not on a closed-out QBR pack (which has not been produced yet at the time QBP runs). The running data is incomplete by design. Note the gap honestly in the pack so the LT does not over-anchor on numbers that will move in the final two weeks.

Strategic bets are human bets. The agent's hypothesis-evidence-spend line is a prompt for human judgement, not a recommendation to execute. Make sure the pack is read in a room where the LT can disagree with the agent.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
