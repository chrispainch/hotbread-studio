---
name: product-launching
description: Use when a solution is already shaped and the next step is to prepare it for rollout, internal alignment, and user-facing documentation. Trigger this for requests about launch briefs, phased rollout plans, target audiences, internal enablement, help doc updates, support readiness, or transparent success measurement tied to the expected outcomes of a feature, product, or solution.
metadata:
  short-description: Prepare solutions for rollout and adoption
---

# Product Launching

Use this skill when the solution is real enough that the work has shifted from defining it to preparing people to use it, support it, and measure it.

## When To Use

Use this skill when the user asks to:
- write an internal launch brief
- prepare rollout communication for a feature, product, or solution
- define who the launch is for and when it happens
- plan phased release or staged audience rollout
- identify which help docs or support docs need updating
- make launch success criteria and measurement explicit
- socialize what changed, why it matters, how to use it, and why the launch should matter to the organization

Typical prompts include:
- "Let's prepare the launch brief."
- "Write the internal and external documentation needed for launch."
- "Define the rollout plan and who this launches to."
- "What help docs need to change before release?"

Do not use this skill when the team is still deciding whether the problem matters. That belongs to `problem-framing`.

Do not use this skill when the bounded shape of the solution is still unclear. That belongs to `solution-shaping`.

Do not use this skill for:
- low-level implementation work
- detailed UI option exploration
- trying to rescue an under-shaped solution with launch messaging

Those belong to implementation, `ascii-ui-exploration`, or more shaping.

## Core Rule

Launch artifacts should make the rollout legible to both internal teams and end users.

The launch work should make these things clear:
- whose problem is being solved
- what is launching
- why it matters now
- what is different with the new solution
- how it should be used
- who gets it and when
- what internal and external docs must exist
- what outcomes are expected for users and for the organization
- how success will be measured after launch

Do not rewrite the shaping document. Build on it.

## Workflow

1. Start from the shaping artifact.
- Use the existing shaped solution as the source of truth.
- Restate the problem, solution, expected user outcomes, and expected organizational outcomes briefly for launch readers.
- If the solution shape is still unstable, stop and return to `solution-shaping`.

2. Define the launch audience.
- State who the launch is for first.
- Be explicit about internal audiences such as GTM, support, ops, or product.
- Be explicit about external audiences such as all users, a subset of captains, a beta cohort, or one account segment.

3. Explain what changed.
- Describe the new capability in plain language.
- Make clear what is different from the old workflow or behavior.
- Include how to use it, not just what it is called.

4. Define rollout.
- State the target launch date or sequence when known.
- If rollout is phased, define the phases clearly.
- Explain who enters each phase and what criteria move the launch forward.

5. Define documentation and enablement needs.
- Identify internal artifacts needed to socialize the launch.
- Identify user-facing help content that must be added or updated.
- Identify support and troubleshooting content that should exist before exposure grows.
- If relevant, point to screenshots, demos, or training material that should be prepared.

6. Define launch readiness and support readiness.
- Capture what must be true before launch.
- Include important quality bars, instrumentation needs, support preparedness, and operational checks.
- Make known risks and fallback paths visible.

7. Define success and measurement.
- Link launch success directly to the expected outcomes from shaping.
- State which metrics are primary and which are supporting.
- Separate user-outcome metrics from organizational-outcome metrics.
- Be transparent about any measurement gaps.
- Include post-launch review checkpoints if useful.

8. End with the next action.
- identify docs to update now
- identify rollout dependencies still blocking launch
- identify whether the team is ready to launch, ready only for a limited release, or still pre-launch

## Output

Produce a launch artifact, usually in `prds/`, using the template in [references/product-launching-template.md](references/product-launching-template.md).

Common outputs include:
- an internal launch brief
- a documentation update plan
- a phased rollout plan

Use filenames that fit the initiative, such as:
- `prds/game_detail_page_launch.md`
- `prds/user_docs_launch_brief.md`
- `prds/bilingual_launch_plan.md`

Follow any repo naming convention already in place.

## Internal And External Docs

At minimum, the launch artifact should identify:
- which internal teams or stakeholders need the brief
- which user-facing help docs must be created or updated
- which support or troubleshooting flows need explicit coverage

Do not assume the launch is complete just because the feature is implemented.

## Organizational Outcome Guidance

Carry forward the organizational outcomes from framing and shaping.

Make explicit:
- why this launch is worth doing for the organization
- what benefits should appear if users adopt the solution
- how those benefits will be recognized after launch
- where attribution is direct versus indirect

This is important for benefit attribution, ROI discussion, and post-launch learning.

## Measurement Guidance

Prefer measures that reflect real post-launch outcomes, such as:
- adoption rate of the new feature or flow
- successful completion rate
- time to first value
- support load or support topic mix
- reduction in confusion, failure, or manual intervention
- retention or repeat usage when relevant
- conversion, expansion, or operating-efficiency outcomes when traceable

Tie the metrics back to the intended outcomes from shaping.

## Handoff

Recommend implementation or doc production work when:
- the launch requirements are clear and the remaining work is execution

Recommend revisiting `solution-shaping` when:
- the launch brief exposes unresolved scope or behavior ambiguity
- rollout decisions depend on missing solution details
