# design-partner-state-agent

> **Status: also-considered.** Real, buildable, but assumes a CRM and customer-success maturity most readers will not have on day one. I cut it from the article because it presupposes a design-partner program already running with named partners, scheduled call cadences, and conversion-readiness tracking. Build it once that program is in place.

**Tier:** LT cadence
**Cadence event:** Monthly design-partner cohort review
**Cadence:** Monthly, on the third business day.

## What it does

Watches each design partner so the drifting one does not show up on a churn list before anyone notices.

## Reads from

- Design-partner CRM records
- Product-analytics usage by partner
- Support-ticket volume and severity by partner
- Scheduled-call cadence and last-touch dates
- Partner-specific feature commitments
- The convert-to-paying milestone tracker

## Produces

- A one-pager per design partner: engagement state (engaged, drifting, dark), last touchpoint, usage trend, open commitments, conversion-readiness flag
- A cohort-level summary: how many partners are on track to convert, how many are drifting, which commitments are blocking conversion

Lands in the product Confluence space.

## Audience

Head of product, design-partner program owner, GM, sales leadership.

## Pain it removes

The drifting design partner that nobody notices until they show up on a churn list.

## Verdict on dream-team originals

**New.**

## Prompt-shape sketch

The prompt tells the runtime to read the design-partner CRM records, usage data, support history, and call-cadence data, and produce a per-partner one-pager plus a cohort summary. Engagement state is a categorical output (engaged / drifting / dark). The conversion-readiness flag is a data-driven prompt for human judgement, not a recommendation.

## Risks and cautions

If design-partner data lives across three systems with no shared identifier, the agent will struggle. Pick a canonical partner ID first.

"Drifting" is a tone-loaded label. The flag should be precise about what drift means (no usage in 14 days, no scheduled call in 30 days) so the program owner can act on the underlying signal, not the label.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
