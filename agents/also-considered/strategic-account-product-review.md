# strategic-account-product-review-agent

> **Status: also-considered.** Real, buildable, but assumes an enterprise customer-success organisation with named strategic accounts, account usage tracking, and an expansion-revenue motion. I cut it from the article for the same reason as design-partner-state-agent: it presupposes a maturity most readers will not have on day one. Build it when your top-ten accounts have account-team channels and customer-success notes that are written in the same place every week.

**Tier:** LT cadence
**Cadence event:** Quarterly strategic-account review for the top-ten paying enterprise accounts
**Cadence:** Runs in the second-to-last week of the quarter.

## What it does

Reviews the top-ten enterprise accounts so the head of product is not spending the weekend reading ten different account-team Slack channels to assemble the picture.

## Reads from

- Customer-success notes
- Account usage data
- Expansion-revenue tracking
- Churn-risk score
- Support-ticket history per account
- Feature-request log per account
- Escalation history

## Produces

- A one-page review per account: usage trend, expansion or contraction signal, churn-risk flag, top three feature requests, top three quality issues, recommended product action
- A cohort summary highlighting any account whose state changed materially this quarter

Lands in the strategic-accounts Confluence space.

## Audience

Head of product, GM, customer-success leadership, sales leadership.

## Pain it removes

The strategic-account review where the head of product spends the weekend reading ten different account-team Slack channels to assemble the picture.

## Verdict on dream-team originals

**New.**

## Prompt-shape sketch

The prompt tells the runtime to read each account's customer-success notes, usage data, support history, and revenue signals, and produce a one-page review per account plus a cohort summary. The recommended product action is flagged as a recommendation, not a decision.

## Risks and cautions

Customer-success notes are written by humans for humans. The agent will sometimes misread context. A human pass before the review is shared is non-negotiable.

Strategic accounts are sensitive. A misread that lands as a churn-risk flag for an account that is fine will damage trust with the customer-success team. Tune carefully.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
