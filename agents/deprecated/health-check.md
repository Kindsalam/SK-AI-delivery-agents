# health-check-agent (deprecated)

> **Status: deprecated.** I am not telling you to build this one. The article explains why in a sidebar. The short version is below.

The dream-team article named a health-check agent that would read retro themes, chat tone, and 1-on-1 patterns and surface burnout signals to leadership.

## Why deprecated

The signal is real. People do burn out. Patterns do show up in chat tone and in 1-on-1 notes. The problem is the engineering and the failure mode.

An agent that scores chat tone is reading every public message your team posts and assigning it a sentiment. The signal is noisy because tone moves with deadlines, with code reviews, with the time of year. The false-positive rate on burnout from chat-tone alone is high.

An agent that reads 1-on-1 notes is reading the most sensitive document the manager-direct relationship produces and asking it to make a judgement on the human in the room. The consent question is open. The privacy question is open. The how-does-the-manager-react-when-the-agent-flags-one-of-their-reports question is open.

If you build this agent and it gets it wrong, you will have a conversation about surveillance with your team. If you build it and it gets it right, you will have a conversation about why the agent noticed before the manager did.

## What to do instead

Burnout signals are picked up better by humans paying attention.

- Make sure your retros surface them. Use the retro-prep-agent's brutal-facts feed and watch for patterns like "team raised wellbeing" turning up across multiple sprints
- Make sure your 1-on-1s have space for the signal to come up. The manager-direct conversation is the channel for this, not a model output
- Watch the leading indicators that your tooling already captures: time-off-balance trending down, on-call load uneven across the team, sprint scope churn climbing without leadership attention

If you still want a model in the loop, run it offline against anonymised aggregate data only. Score the *team*, not the *person*. And do not post the output anywhere automatically. The manager looks at the score, asks themselves if the team feels right, and uses the score as a prompt to listen harder. That is a different agent and a different shape.

## Verdict on dream-team originals

**Deprecate.**


---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
