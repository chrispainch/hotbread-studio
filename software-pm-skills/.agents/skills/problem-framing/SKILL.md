---
name: problem-framing
description: Use when the work is still at the problem stage and needs a framing artifact before solution shaping. Trigger this for requests centered on a user need, pain point, gap, opportunity, or vague feature idea where the goal is to clarify what problem is worth solving, why it matters, how painful it is, what better user outcome would look like, and what organizational upside would follow without locking into a solution.
metadata:
  short-description: Frame user needs before shaping solutions
---

# Problem Framing

Use this skill when the user is not ready to define the solution yet and wants to understand the problem clearly enough to decide whether it is worth solving.

## When To Use

Use this skill when the user asks to:
- explore a user need, pain point, friction, or missed opportunity
- describe a gap between the current state and a better user outcome
- rank or compare problems by urgency, value, or pain
- write a brief that explains the need before solution design
- clarify who is struggling, why, how much it matters, and why the organization should care

Typical prompts include:
- "Let's frame this problem."
- "Write a brief in `prds/` about this need."
- "I want to understand the user problem before designing the solution."
- "Help me define the gap and why it matters."

Do not use this skill when the user is already asking for:
- solution boundaries, components, or included/excluded scope
- UI layouts, wireframes, or detailed interaction options
- implementation plans, migrations, routes, schemas, or rollout tasks

Those belong to `solution-shaping`, `ascii-ui-exploration`, or implementation work.

## Core Rule

Stay at the problem level.

The framing artifact explains:
- whose need exists
- what gap exists today
- why the gap matters
- how painful or costly the gap is
- how life improves if the need is satisfied
- what positive organizational outcomes would likely follow if the user outcome is achieved

It must not prescribe the solution in detail.

## Workflow

1. Identify the user and the need.
- Name the primary user clearly.
- State the job they are trying to get done.
- Distinguish the need from any proposed feature.

2. Describe the current gap.
- Explain the current workflow, workaround, failure mode, or friction.
- Make the gap concrete and observable.
- If useful, use `breadboarding` to map the current workflow and where pain appears.
- When using `breadboarding`, prefer the flowchart-ready table artifact so broken screens, affordances, and transitions are explicit.

3. Assess pain and value.
- Capture qualitative pain: confusion, wasted time, missed trust, operational risk, lost revenue, etc.
- Estimate quantitative signals when available: frequency, reach, conversion loss, support load, time cost, churn risk, missed usage.
- Do not invent numbers. If data is unavailable, say so and use directional confidence.

4. Define the better user outcome.
- Describe what becomes easier, safer, faster, clearer, or more valuable for the user if the need is satisfied.
- Keep this outcome user-facing, not implementation-facing.

5. Define the organizational outcome.
- Translate the user outcome into likely benefits for the organization.
- Examples: higher activation, better retention, more usage, fewer support contacts, stronger conversion, lower operational cost, clearer product differentiation, improved trust.
- Call out where the relationship is strong, weak, or still hypothetical.

6. Isolate the problem statements.
- Extract a short set of problem statements from the evidence.
- Prefer crisp statements over broad themes.

7. Surface uncertainty.
- List open questions, missing evidence, and assumptions.
- Say what would most change the priority or framing if learned.
- Include any uncertainty in outcome attribution.

8. End with a recommendation.
- State whether the problem appears worth advancing to `solution-shaping`.
- If several problems are present, rank them or recommend which to shape first.

## Output

Produce a framing artifact, usually in `prds/`, that follows the template in [references/framing-template.md](references/framing-template.md).

Use a filename that reflects the problem or need, such as:
- `prds/player_invite_consent_framing.md`
- `prds/mobile_navigation_framing.md`
- `prds/user_docs_need_framing.md`

If the repo already has a naming convention, follow it.

## Scoring Guidance

When ranking or comparing problems, use lightweight scoring if it helps:
- Pain severity: `1-5`
- Frequency: `1-5`
- Reach: `1-5`
- Confidence: `1-5`
- Strategic fit: `1-5`

Do not force scoring when the user only wants a narrative brief.

## Organizational Outcome Guidance

Do not stop at "the user would be happier."

Name the organizational value that would likely follow from the user outcome, such as:
- more successful activation
- improved conversion to paid usage
- better retention or repeat engagement
- lower support burden
- reduced manual operations
- improved data quality or operational reliability
- stronger competitive position

Keep attribution honest. If the connection is indirect or uncertain, say so.

## Breadboarding

Use `breadboarding` when the workflow itself is unclear or when the pain emerges across multiple steps.

In framing, breadboards should focus on:
- the user's current path
- where handoffs happen
- where friction, delay, confusion, or failure appears
- what components already exist and how they are broken or fragmented

Prefer the standard table format so the artifact can later translate into a flowchart.

Do not turn breadboards into screen design. That belongs later.

## Handoff

Recommend `solution-shaping` only when the framing artifact is clear on:
- the user
- the need
- the gap
- why it matters
- what better user outcome is desired
- what organizational upside makes the problem worth solving

If any of those are still muddy, keep working in framing instead of jumping ahead.
