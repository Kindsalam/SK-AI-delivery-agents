# portfolio-bets-readout-agent

**Tier:** LT cadence
**Cadence event:** Monthly executive readout to the steering committee or board
**Cadence:** Monthly, five business days before the steering meeting (so the LT has time to read the doc before the meeting rather than walking in cold).

## What it does

Prepares the monthly steering or board readout so the head of product is not writing the same narrative paragraphs they wrote last month with different numbers.

## Reads from

- The strategic-bets register
- North-star metric trend
- OKR scorecard
- Capacity allocation by bet
- Design-partner state
- Win/loss themes for the month
- Top three open executive questions from the prior month's readout

## Produces

A short executive-grade document:
- One page per strategic bet covering hypothesis, evidence-to-date, current spend versus committed, time-since-last-pivot, plus a colour-coded signal per bet on each of those four dimensions
- A one-page cover with north-star trend and OKR scorecard

The LT names the action. The signal is a data prompt, not a kill-or-double-down recommendation in disguise. Lands in the steering Confluence space.

## Audience

Steering committee, board, GM, head of product.

## Pain it removes

The monthly steering pack where the head of product writes the same narrative paragraphs they wrote last month with different numbers.

## Verdict on dream-team originals

**New.** The dream-team project-or-product-updates-agent at LT scale becomes the QBR pack at quarter-end and the portfolio readout monthly. Different cadence, different artefact.

## Prompt-shape sketch

The prompt tells the runtime to assemble a one-page-per-bet executive document. The hypothesis, the evidence-to-date, the spend versus committed, the time since the last pivot, and a colour-coded signal on each of those four dimensions based on agreed thresholds. The cover page carries the north-star trend and OKR scorecard. The agent surfaces signals on the underlying data. The LT names the action.

## Risks and cautions

The colour-coded signals are the most visible part of the readout. A wrong signal will erode trust in the agent quickly. The thresholds (what counts as red on spend-vs-committed, what counts as red on time-since-last-pivot) have to be agreed with the LT before the agent runs. Otherwise the agent picks defaults and the LT spends the meeting arguing about the thresholds rather than the bets.

A monthly readout is only useful if the steering committee reads it. If the committee uses the meeting to be briefed rather than to decide, the agent is helping the wrong meeting. Push for the committee to read the doc before the meeting. The five-business-day cadence is intentional.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
