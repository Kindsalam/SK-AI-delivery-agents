# integration-readiness-agent

**Tier:** Scrum of Scrums / multi-team coordination
**Cadence event:** Cross-team integration / system demo (in SAFe, the System Demo at PI cadence; in plain Scrum, the integration milestone)
**Cadence:** Runs daily during the week leading up to the integration date, then continuously the day of.

## What the team gets

During the week leading up to a system demo or integration milestone, this agent has already given the room an honest go / no-go before anyone walks in. The RTE and tech leads walk in to a card showing per-team status, what specifically is blocking each team, draft proposed unblock actions per blocker (with proposed owner and the next test that needs to pass), the smallest set of decisions needed to unblock, and a projected confidence level on the go decision.

What the room stops doing: opening the meeting with thirty minutes of "is everyone ready" and then making a hurried go/no-go call in the last ten minutes. The conversation starts where it should: at the blockers and the decisions that unblock them.

The final call is the room's. The agent assembles the data and drafts the unblock actions. The room decides go or no-go, accepts or edits the unblock actions, and owns the consequences.

## Reads from

- Branch state across all participating repos (GitHub)
- Integration-environment deploy status (CI/CD)
- Feature-flag state for the integration in question
- Integration test pass rates
- Contract-test results for cross-team APIs
- Cross-team Jira items tagged for this integration

## Produces

An integration readiness card in the SoS channel and pinned to a Confluence integration page:
- Per-team status: ready / not ready / blocked
- Specific blockers per team
- Draft proposed unblock actions per blocker (with proposed owner and the next test that needs to pass), marked clearly as `[draft, room to confirm]`
- Smallest number of decisions needed to unblock
- Projected go / no-go with a confidence level (low / medium / high based on how many blockers are decisions versus dependencies)

## Audience

RTE, principal engineer, tech leads, group product manager.

## Pain it removes

Every team thinking the others are ready while one team is silently three days behind.

## Verdict on dream-team originals

**New.** The dream-team did not name integration as a cadence event.

## Prompt-shape sketch

The prompt tells the runtime to read each participating team's branch state, feature-flag state, test pass rates, and contract-test results, and produce a per-team go / no-go with a named blocker per team if not ready. The prompt tells the runtime to identify the smallest set of unblocking decisions and project a go / no-go with a confidence level (low / medium / high) based on how many of the blockers are decisions versus dependencies. The agent does not make the call. It assembles the data so the room can.

## Risks and cautions

If integration tests do not exist, the agent will report "no test data" and the room will be tempted to go anyway. Treat the absence of tests as a no-go signal, not a missing-data signal.

Confidence levels can become a comfort blanket. A "high confidence go" with two known blockers is not a go. The card shows the data. Humans read it.

Contract-test result reading is the input most likely not to have an MCP server today. Pact Broker, Spring Cloud Contract, Postman contract tests, none have shipped MCP servers as of mid-2026. Most teams will need to wrap their contract-test broker with a thin adapter or fall back to reading the CI job's pass/fail signal.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
