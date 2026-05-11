# standup-update-agent

**Tier:** Team Scrum cadence
**Scrum event:** Daily Scrum
**Cadence:** Daily, generated 06:00-08:00 team-time, posted before 09:00. Two passes if the team is split across time zones.

## What it does

Writes the overnight one-pager so the team walks into standup already informed. The round-the-room status ritual disappears. The conversation in the room shifts to what is blocked, unclear, or worth changing today.

## Reads from

- Git commits and PRs since the previous evening (GitHub)
- Jira ticket transitions on the active sprint board
- Slack or Microsoft Teams team-channel messages since the previous evening
- The active Sprint Goal as recorded in Jira sprint metadata or Confluence

## Produces

A one-page markdown post in the team channel. Sections: Shipped, Stalled, Sprint Goal trajectory (on track / drift / off), likely standup talking points. Every claim links back to a commit, ticket, or thread. Same document on every desk before the Daily.

## Audience

Whole dev team, product owner, scrum master, engineering lead. Read before walking into the Daily.

## Pain it removes

The round-the-room status ritual where each person reads out what they did yesterday.

## Verdict on dream-team originals

**Take.** Already deep-dived in [make your standup a planning event again](https://salamkhan.au/blog/make-your-standup-a-planning-event-again). The shape was right. Use as-is.

## Prompt-shape sketch

The prompt tells the runtime to read commits, PR activity, ticket transitions, and team-channel messages from the previous evening through to this morning. It tells the runtime to write a one-page update in plain English, structured by Shipped / Stalled / Sprint Goal trajectory / likely standup talking points. It tells the runtime to link every claim to a commit, ticket, or thread, and to keep the language a normal team member would use, not a manager-deck-flavoured summary.

## Risks and cautions

Stale tickets will produce stale updates. The agent only knows what the systems know. The first week of running it will surface tickets nobody has updated in a fortnight. Treat that as a feature, not a bug.


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
