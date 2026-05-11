# portfolio-sprint-rollup-agent

**Tier:** Scrum of Scrums and multi-team coordination (portfolio scale)
**Cadence event:** Portfolio sprint review / department-level fortnightly readout
**Cadence:** End of every sprint (typically fortnightly), the morning after each program's multi-team-sprint-rollup runs.

## What the portfolio leader gets

At the end of every sprint, this agent has already stitched together what happened across every program in the portfolio. The portfolio leader walks in to a single document with a portfolio-level paragraph at the top, one paragraph per program covering Sprint Goal verdict and headlines, the movement of the strategic bets, the cross-program risks that compounded, and the open questions for the portfolio table.

What the portfolio leader stops doing: chasing every program manager for a status before each fortnightly portfolio review. Hand-assembling a rollup deck nobody is sure is current. Walking into the portfolio prioritisation conversation cold because there has been no time to assemble the cross-program picture.

The final call is the portfolio leader's. The agent rolls up the data; the leader interprets and acts.

## Reads from

- Each program's multi-team-sprint-rollup output (from each ART or program in scope)
- Portfolio-level OKR scorecard subset (the KRs that the portfolio is tracking, not every team-level KR)
- Strategic-bets register
- Cross-program dependencies if tracked (the dependency matrix that crosses ART boundaries)
- Customer escalations tagged to portfolio-level initiatives
- Portfolio milestones and deadlines from the portfolio plan
- Last sprint's portfolio-rollup for delta tracking

## Produces

A portfolio-level rollup landed in the portfolio Confluence space, mirrored to a portfolio Slack channel.

Sections:

- **Portfolio-level paragraph at top.** Summarises what the data says about the sprint just ended at portfolio scale. One paragraph, plain English.
- **One paragraph per program.** Sprint Goal verdict (hit / partial / missed), headline of what shipped, what slipped, what is at risk against the program's committed quarter.
- **Strategic-bets status update.** How each bet moved this sprint. New evidence, new spend, new confidence.
- **Cross-program risks that compounded this sprint.** From the program-risk-radar outputs across programs.
- **Open questions for the portfolio leadership table.** What does the portfolio leader need to decide in the next fortnight?

## Conventions the agent follows

- **Reads the program-level rollups, does not read raw Jira at portfolio scale.** Each program's multi-team-sprint-rollup-agent is the canonical input. Reading raw Jira across the portfolio is too noisy and bypasses the program-level interpretation that has already happened.
- **Lands in the portfolio Confluence space**, mirrored to the portfolio Slack channel. Does not land in any single program's space.
- **Never updates the strategic-bets register, the OKR scorecard, or any program's rollup directly.** The portfolio leader updates the canonical artefacts after the readout.
- **Plain English, leadership audience.** No deck-flavoured headers. No squad-internal jargon that did not survive the program-level rollup.

## Audience

- **Primary:** portfolio manager / portfolio director, head of engineering at portfolio scale, head of product at portfolio scale.
- **Secondary:** COO / CTO if the portfolio sits at C-suite level.
- **Tertiary:** steering committee in larger orgs, board in smaller orgs.

## Pain it removes

The portfolio leader hand-assembling a rollup deck every fortnight by chasing five program managers for status. The portfolio prioritisation conversation that starts cold because nobody has had time to assemble the cross-program picture. The fortnightly meeting where the first hour goes to "what happened" and the second hour to "what next" without enough time for either.

## Verdict on dream-team originals

**New.** The dream-team article had no portfolio-cadence equivalent. This is the agent that closes the gap between Tier 2 program rollups (one ART per agent) and Tier 3 LT readouts (quarterly cadence) at sprint cadence. Portfolio leaders currently get a clean view at quarter-end via QBR. This agent gives them a clean view every fortnight.

## Prompt-shape sketch

The prompt tells the runtime to read each program's multi-team-sprint-rollup output, the portfolio-level OKR scorecard subset, the strategic-bets register, and any cross-program dependencies. The prompt tells the runtime to assemble a portfolio-level rollup with the fixed sections above, written in plain English for a leadership audience. The prompt explicitly forbids the agent from reading raw Jira at portfolio scale (each program's rollup is the canonical input) and from updating any canonical artefacts. The agent stitches and writes; the portfolio leader interprets and decides.

## Risks and cautions

**Run shadow mode for the first two sprints.** This is a portfolio-level agent and the audience is C-suite-adjacent in many orgs. Drafts in plain text for two sprints (longer than the team-tier shadow window) so the portfolio leader can correct the shape and the framing before it is automated. Then enable Confluence write access where the agent updates the portfolio Confluence page directly.

**Garbage in, garbage out applies harder at portfolio scale.** If the program-level multi-team-sprint-rollups are themselves noisy or inconsistent, this agent's output will be noisier and less consistent. Get the program-level rollups working cleanly for two or three sprints before turning this on.

**Programs run on different cadences sometimes.** If one program runs three-week sprints and the others run two-week, the rollup either has to wait for the slowest program or has to ship with one program's data missing. State the convention up front: ship on the portfolio's fastest cadence, name programs whose data is older than a sprint.

**Strategic-bets movement can read as recommendation.** When a bet's evidence has not moved for three sprints, the agent's "no movement" line will read like a kill-the-bet flag. The agent does not flag kill or double-down (that is the portfolio-bets-readout-agent's job, monthly). Keep the language descriptive.

**The portfolio leader is the only audience that should rely on this agent.** Programs reading their own line in the portfolio rollup will be tempted to react to wording they did not control. Make sure each program's rollup is the canonical view of that program; the portfolio rollup is for the portfolio audience.

---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
