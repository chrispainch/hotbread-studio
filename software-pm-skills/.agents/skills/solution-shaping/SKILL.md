---
name: solution-shaping
description: Use when a problem is already framed and the next step is to define the bounded shape of the solution before UI refinement or implementation. Trigger this for requests about solution scope, included and excluded behaviors, full-stack components, key risks, success criteria, measurement, sequencing, or a document in `prds/` that should guide implementation without dropping into low-level build steps.
metadata:
  short-description: Define the shape of the solution space
---

# Solution Shaping

Use this skill when the problem is clear enough and the work now needs a robust definition of the solution space.

## When To Use

Use this skill when the user asks to:
- shape a solution after the problem has been framed
- define what is in scope and out of scope
- break an initiative into self-contained full-stack components
- describe the intended flow and boundaries before implementation
- write a `prds/` document that should guide implementation
- define success criteria and how they will be measured

Typical prompts include:
- "Let's shape the solution."
- "Turn this into a document that will guide implementation."
- "Write the PRD in `prds/`."
- "Define the scope, components, risks, and success metrics."

Do not use this skill when the user is still deciding whether the problem matters. That belongs to `problem-framing`.

Do not use this skill for:
- detailed screen-level UI option work
- low-level implementation plans, migrations, route handlers, or schema edits
- launch enablement, rollout communications, or help content updates

Those belong to `ascii-ui-exploration`, implementation work, or `product-launching`.

## Core Rule

Shape the solution without over-specifying the build.

The shaping artifact should make these things clear:
- what solution is being proposed
- what its boundaries are
- what it includes and excludes
- what components it contains
- what each component solves
- what risks and constraints matter
- what success looks like for the user and for the organization
- how success will be measured
- how the expected organizational value connects back to the user outcome

It should not turn into a step-by-step engineering task list unless the user explicitly asks for that afterward.

## Workflow

1. Confirm the problem being addressed.
- Start from an existing framing artifact when available.
- If the problem is still fuzzy, stop and return to `problem-framing`.
- Restate the need, gap, intended user outcome, and intended organizational outcome briefly at the top of the shaping doc.

2. Define the solution boundary.
- State what the solution is meant to accomplish.
- Make included and excluded scope explicit.
- Draw the line around v1 or the current slice.

3. Describe the solution flow.
- Explain the intended user or system flow at a high level.
- Use `breadboarding` when the flow spans several steps, states, or handoffs.
- Prefer a breadboarding table that can translate almost directly into a flowchart.
- Keep this at the flow level, not the final screen design level.

4. Break the solution into components.
- Prefer full-stack components that are as self-contained as possible.
- Each component should be understandable on its own by both humans and the implementation agent.
- Avoid splitting by technical layer only.

5. For each component, explain:
- the part of the gap it addresses
- why it exists
- the user-facing outcome it supports
- the organizational outcome it should contribute to
- the major risks or edge cases
- key implementation details to be aware of
- dependencies or sequencing constraints

6. Define success and measurement.
- State what success looks like for the user and for the business or product.
- Define how it should be measured.
- Include both qualitative and quantitative measures when relevant.
- If a metric is not yet instrumented, say so.
- Separate leading indicators from lagging indicators when useful.

7. Surface open questions.
- Record unresolved decisions that could change scope or architecture.
- Keep these visible instead of burying them in chat.
- Include outcome-attribution uncertainties when relevant.

8. End with the recommended next step.
- hand off to `ascii-ui-exploration` when a component needs screen or interaction refinement
- hand off to implementation when the shape is already clear enough
- hand off to `product-launching` only after the solution is real enough to prepare rollout materials

## Output

Produce a shaping artifact, usually in `prds/`, using the template in [references/solution-shaping-template.md](references/solution-shaping-template.md).

Use a filename that reflects the initiative, such as:
- `prds/game_detail_page.md`
- `prds/account_user_domain_refactor.md`
- `prds/profile_and_user_access_management.md`

Follow any repo naming convention already in place.

## Breadboarding

Use `breadboarding` when the solution needs a high-level workflow map.

In shaping, breadboards should focus on:
- major states
- transitions and handoffs
- component boundaries
- what happens before and after the user-visible action
- what needs to exist for the solution to work

Prefer the standard table format so the artifact can later translate into a flowchart.

Do not use breadboards as a substitute for final UI design.

## Component Guidance

A good shaping component is:
- meaningful to the user or operator
- testable as a slice of behavior
- full-stack enough to produce real value
- narrow enough that scope and risk are understandable

Weak components are:
- vague themes
- purely technical buckets like "backend" and "frontend"
- giant initiatives with no clear completion boundary

## Organizational Outcome Guidance

Carry forward the organizational value identified during framing.

For each major part of the solution, make clear how it is expected to help the organization, such as through:
- revenue or conversion lift
- retention or repeat usage
- operational efficiency
- support cost reduction
- improved reliability or trust
- better data quality
- strategic differentiation

If the link between user value and org value is indirect, state the hypothesis instead of pretending it is proven.

## Success Metrics Guidance

Prefer measures that can later validate whether the shaped solution actually worked, such as:
- activation or completion rate
- time to complete the workflow
- support burden or confusion reduction
- error rate or recovery rate
- adoption of the new flow
- operational workload removed from the captain or internal team
- downstream business impact when traceable

Do not invent precision. Use hypotheses where needed.

## Handoff

Recommend `ascii-ui-exploration` when:
- a shaped component has meaningful interface ambiguity
- information hierarchy or interaction model is still open
- the feature needs screen-level option exploration

Recommend implementation when:
- the boundaries, components, risks, success criteria, and organizational outcomes are clear
- the remaining work is primarily execution
