# refinement-prep-agent

**Tier:** Team Scrum cadence
**Scrum event:** Backlog Refinement (Product Backlog Refinement in the Scrum Guide)
**Cadence:** Runs when an Epic is signed off (event-triggered), and again the morning of refinement.

## What it does

First-pass story drafting before Backlog Refinement, so the session becomes a real discussion instead of a writing exercise. The agent reads the Epic, learns from previous stories Done, looks at what the backlog already has, drafts the missing stories directly into Jira (in `Draft` status), and produces the refinement agenda. The product owner reviews and sharpens the drafts. The team refines the sharpened versions in the session.

This agent becomes your first-pass BA/PO. The actual product owner stays in charge of priority, scope, and final wording. The agent shifts the PO from typist to editor.

## Reads from

- The parent Epic in Jira: description, Epic-level acceptance criteria, parent Initiative link
- Linked design pages in Confluence under the Epic
- Previous stories Done under this Epic and under similar Epics: titles, acceptance criteria, story-point estimates, components used, labels applied (the pattern library the agent learns from)
- The current backlog under the Epic: what is already there, what is missing relative to the Epic's scope
- The team's Definition of Ready as the bar to draft against
- The component / ownership matrix in Confluence
- Any technical spike outcomes or customer-feedback items linked to the Epic

## Produces

Two outputs.

### 1. Draft new stories in the Jira backlog

Each draft story is created with:

- **Status:** `Draft` (a status that sits before the active backlog so sprint planning cannot pull it accidentally)
- **Label:** `agent-drafted` (removed when the PO sharpens the story; that is the human review signal)
- **Parent Epic link:** populated
- **Title:** draft, in plain English
- **Description:**
  ```
  ## Context
  [Why this story exists, drawn from the Epic and the gap analysis]

  ## Acceptance criteria (draft)
  - Given... when... then...
  - Given... when... then...

  ## Pattern source
  Drafted by refinement-prep-agent on [date]. Patterns from these prior stories: [list of links to Done stories the agent referenced].
  PO to review.
  ```
- **Story-point estimate:** rough, drawn from the median of comparable Done stories
- **Component:** inherited from the Epic. If the Epic touches multiple components, the agent picks the most likely based on the story content and notes the alternatives in the description
- **Reporter:** the agent's service account (so the audit trail shows who drafted)

### 2. The refinement agenda

Same as the original informative shape:

- Ready to refine: items the team can refine in session, with what is missing per item
- Not ready, parking lot: items that need a PO conversation before the team's time
- Already DoR-clean: skip in session

Lands in the team channel and is pinned to the Confluence refinement page.

## Conventions the agent follows

- **Label `agent-drafted`** on every story it creates. PO removes the label when they accept the story (or moves it to `Refined`, or whatever status the team's workflow uses).
- **Status `Draft`** so the story is invisible to sprint planning until promoted.
- **Component inherited from the Epic** unless the agent has high-confidence reason to pick a different one (in which case the alternative is in the description, not the Component field).
- **No `Story Points` set in stone.** The estimate is a rough median from comparable Done stories. The team revises during refinement.
- **No `Sprint` assignment.** Even if capacity exists. The PO promotes; sprint planning pulls.

## Audience

- **Primary:** product owner, product manager. They review and sharpen the drafts before refinement.
- **Secondary:** tech lead. Sanity-checks technical feasibility on the agent's drafts.
- **Final:** dev team. Refines the sharpened versions in session.

## Pain it removes

The product owner spending hours drafting stories from scratch, then arriving at refinement with half-formed items the team has to reshape on the fly. The session becomes a writing exercise instead of a discussion. With this agent, the PO walks in with first-pass drafts already in the system, sharpens them based on judgement and context the agent does not have, and the refinement session is where humans argue about real trade-offs.

## Verdict on dream-team originals

**New.** The dream-team article did not name this one. It is the highest-leverage Tier 1 add because refinement is the event most teams agree they do badly, and because the agent here can do real first-pass authoring rather than just informational prep.

## Prompt-shape sketch

The prompt tells the runtime to read the Epic and its parent Initiative, gather the Done stories under this Epic and similar Epics as a pattern library, read the current backlog under the Epic, and identify the gaps between what the Epic asks for and what the backlog already covers. The prompt tells the runtime to draft new stories filling those gaps, each with a draft title, draft acceptance criteria in Given/When/Then form, an estimate from the median of comparable Done stories, the inherited component, and a notes section pointing at the prior-story patterns. The prompt explicitly forbids the agent from setting status to `To Do` / `Backlog` or assigning a Sprint. Every drafted story lands in `Draft` status with the `agent-drafted` label, and the PO promotes from there.

## Risks and cautions

**Run shadow mode for the first week.** This agent breaks the read-only-first principle by design: it has to write to Jira to create stories. The first version of the agent should draft in plain text and post the drafts to a channel for the PO to create the Jira tickets manually. After a week of the PO trusting the output, enable Jira write access where the agent creates tickets directly in `Draft` status. The `Draft` status is the safety gate. Agent-drafted stories must never enter a sprint until a human promotes them.

**Hallucinated stories are the failure mode.** The agent might invent stories for problems that do not exist, or draft duplicates of stories that already exist (because the agent missed an existing item in the backlog). The PO catches both of these. If the PO accepts agent drafts blindly without thinking, the backlog fills with shaped-but-empty work. The label and the `Draft` status protect against this; the PO still has to read.

**Story-point estimates from an agent are guesses, not commitments.** Treat the median from comparable Done stories as a starting frame for the team's planning poker, not as a number to plan against.

**Pattern library quality matters.** Without enough Done stories, or with a backlog full of inconsistent old stories, the agent's drafts will reflect the noise. Encourage the team to keep older Done stories well-structured (or at minimum, link the few that are exemplar to the Epic so the agent prioritises those patterns).

**Without good Epic shape, the agent's drafts are noise.** If the Epic is two sentences and a vague title, the agent has nothing to draft against. The Epic-level shape is the upstream input that determines everything downstream. The product manager owns the Epic; the agent only authors stories under a real Epic.

**Distinct from refinement of the existing backlog.** The agent drafts new stories. It does not edit existing stories the team has already shaped. Editing existing stories is a PO action, not an agent action, because changes to existing stories carry context the agent does not have.

---

*Part of [SK-AI-delivery-agents](https://github.com/Kindsalam/SK-AI-delivery-agents). See the [companion article](https://salamkhan.au/blog/ai-enabled-delivery-the-agent-catalog) for context.*
