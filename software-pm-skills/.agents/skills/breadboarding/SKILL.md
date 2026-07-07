---
name: breadboarding
description: Use when the work needs a UX flow map that shows the current screen, the affordance a user can take, the next screen or state it leads to, what components are involved, and what technical constraints matter. Trigger this for current-state or target-state workflow mapping in problem framing or solution shaping, especially when the artifact should translate almost directly into a flowchart.
metadata:
  short-description: Map UX flows into flowchart-ready tables
---

# Breadboarding

Use this skill when the main need is to map the structure of a workflow before screen-level design or implementation.

## When To Use

Use this skill when the user asks to:
- map a current workflow to expose friction or breakage
- map a target workflow to show what must exist for the solution to work
- identify components, screens, affordances, and transitions in a flow
- create a UX artifact that can translate almost directly into a flowchart
- understand how frontend and backend interactions connect across a flow

Typical prompts include:
- "Let's breadboard this flow."
- "Map the current workflow first."
- "Show the target flow as a table."
- "What exists today and what needs to exist?"

Do not use this skill for:
- deciding whether the problem matters overall
- defining full product scope and v1 boundaries
- screen-level layout options or visual hierarchy exploration
- detailed implementation planning

Those belong to `problem-framing`, `solution-shaping`, `ascii-ui-exploration`, or implementation work.

## Core Rule

Breadboarding is about flow topology, not visual styling.

The artifact should make visible:
- where the user is now
- what affordance they can take there
- where that affordance leads next
- what components exist or need to exist
- how components interact
- what is broken, missing, or constrained
- whether an interaction is primarily `FE`, `BE`, or `FE+BE`

The output should be structured so it can be translated into a flowchart with minimal reinterpretation.

## Workflow

1. Define the mapping goal.
- State whether you are mapping the current flow, target flow, or both.
- State the user goal the flow is meant to serve.
- If the flow belongs to a broader initiative, name the related shaping or framing artifact.

2. Identify the current and next screens or states.
- Keep each row anchored in a specific current screen or state.
- Name the next screen or state that the affordance leads to.
- If the action stays on the same screen but changes the state, name that resulting state explicitly.

3. Identify the affordances.
- Give each affordance a short name.
- Add a short description of the interaction.
- If several affordances lead to materially different branches, split them into separate rows.

4. Describe the transition.
- Make the row readable as an arrow: current screen -> affordance -> next screen.
- Prefer behavioral clarity over implementation detail.
- Make loops, confirmations, dead ends, and branching visible.

5. Capture component and stack implications.
- Name the component or capability involved when it matters.
- Mark each interaction as `FE`, `BE`, or `FE+BE`.
- Use technical notes to record constraints, missing pieces, validation rules, or data dependencies.

6. Call out what exists versus what needs to exist.
- In current-state breadboards, identify what is broken, fragmented, or missing.
- In target-state breadboards, identify what new components, states, or transitions are required.

7. End with implications.
- For framing: identify where the pain concentrates.
- For shaping: identify what components or transitions the solution must support.
- For UI exploration: identify which screens need hierarchy work next.

## Output

Use the table format in [references/breadboarding-template.md](references/breadboarding-template.md).

The standard columns are:
- Current screen
- Affordance name
- Affordance description
- Next screen
- Interaction type
- Technical notes

This table should be readable as a flow artifact and convertible into a flowchart with minimal rewriting.

## Column Guidance

### Current screen

Usually a screen, page state, modal state, confirmation state, or important step the user is currently on.

### Affordance name

A short label for the action, such as `Submit RSVP`, `Open game`, `Confirm invite`, or `Edit settings`.

### Affordance description

A short description of what the interaction actually is or what the user is doing.

### Next screen

What screen or state the user reaches after the action. If the user stays in place but the state changes, name that resulting state.

### Interaction type

Use:
- `FE` for mostly interface-local behavior
- `BE` for mostly backend-driven transitions or processing
- `FE+BE` for cross-stack actions

### Technical notes

Capture:
- key constraints
- important missing capabilities
- validation rules
- data dependencies
- areas where the flow is currently broken or fragile

## Current-State vs Target-State

For current-state mapping, emphasize:
- what exists now
- where the flow breaks
- where context is fragmented
- what users or operators must work around

For target-state mapping, emphasize:
- what needs to exist
- how the components should interact
- what transitions are necessary for the solution to work
- what technical constraints could weaken the intended UX

## Flowchart Readiness

Write rows so they can become nodes and labeled edges almost directly.

That means:
- one meaningful current screen per row when possible
- a short, stable affordance name
- a clear next screen or resulting state
- explicit branching when needed
- minimal ambiguity in transition language

## Handoff

Recommend `problem-framing` when the breadboard shows pain concentration but the actual problem is not yet crisply stated.

Recommend `solution-shaping` when the breadboard makes clear what components and transitions the solution must include.

Recommend `ascii-ui-exploration` when the flow is clear but a screen or component still needs interface hierarchy exploration.
