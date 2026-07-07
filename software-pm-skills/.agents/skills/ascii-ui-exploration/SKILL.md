---
name: ascii-ui-exploration
description: Use when a solution or component is already shaped and the next step is to explore interface options in text before implementation. Trigger this for requests about screen structure, information hierarchy, action hierarchy, interaction patterns, page layout options, or ASCII UI concepts where the goal is to compare directions, explain tradeoffs, and recommend a stronger interface shape without reopening product strategy.
metadata:
  short-description: Explore UI options with ASCII concepts
---

# ASCII UI Exploration

Use this skill when the product direction is clear enough and the remaining ambiguity is mainly about how the interface should be structured, prioritized, and experienced.

## When To Use

Use this skill when the user asks to:
- show UI options before implementing
- draw ASCII layouts or compare interface directions
- rethink information hierarchy on a page or flow
- refine action hierarchy or visual emphasis
- simplify a confusing page or card
- explore where content, controls, and states should live

Typical prompts include:
- "Show me ASCII options before implementing."
- "Give me UI/UX options for this page."
- "How should this card be structured?"
- "Let's explore the interface shape first."

Do not use this skill when the user is still defining the problem. That belongs to `problem-framing`.

Do not use this skill when the solution boundaries, scope, or components are still unclear. That belongs to `solution-shaping`.

Do not use this skill for:
- low-level engineering design
- rollout or documentation planning
- pixel-perfect visual styling work as the primary task

Those belong to implementation work or `product-launching`.

## Core Rule

Explore the interface without reopening strategy.

The goal is to clarify:
- what the user should notice first
- what the primary action is
- what is secondary or peripheral
- how the page or component should be organized
- what tradeoffs exist between interface options

Do not drift into generic design language. Keep the work concrete and tied to the shaped solution.

## Workflow

1. Start from the shaped solution.
- Use the shaped component or flow as the source of truth.
- Restate the user goal, the page or component being explored, and what should remain unchanged.
- If the solution shape is still unstable, return to `solution-shaping`.

2. Identify the UI decision to make.
- Be explicit about what is open.
- Examples: card hierarchy, page header actions, section grouping, action placement, mobile behavior, status visibility, or flow sequencing.

3. Define the hierarchy.
- State what is primary, secondary, and peripheral.
- Clarify which information and actions deserve the most visual weight.
- Clarify what should be de-emphasized or moved out of the primary path.

4. Generate options.
- Produce a small set of distinct ASCII options.
- Each option should represent a real tradeoff, not cosmetic variation.
- Keep options concrete enough that the user can choose a direction.

5. Explain each option.
- For each option, say how it serves the user goal.
- Call out strengths, weaknesses, and likely risks.
- Explain what kind of user behavior or reading pattern each option supports.

6. Recommend a direction.
- Recommend one option when possible.
- Explain why it best fits the shaped solution.
- If the best answer depends on a missing decision, name that dependency clearly.

7. Refine after selection.
- Once the user picks a direction, deepen only that direction.
- Clarify spacing intent, grouping, placement of secondary items, and behavior across states or screen sizes.
- Avoid generating endless new options unless the selected direction breaks down.

## Output

The output is usually conversational exploration plus optional support material using the template in [references/ascii-ui-template.md](references/ascii-ui-template.md).

Typical outputs include:
- 2-4 ASCII layout options
- a recommended direction
- a refined ASCII version of the chosen direction
- notes on what the implementation should preserve

This skill usually supports a shaping artifact or implementation task rather than creating the main source-of-truth document itself.

## Option Quality Rules

Good options should differ by:
- hierarchy
- grouping
- action placement
- sequence of attention
- interaction model

Weak options are:
- visually different but structurally identical
- broad design vibes with no layout consequences
- options that violate already-shaped product rules

## ASCII Guidance

ASCII should help the user reason about layout and hierarchy quickly.

Use it to show:
- headers and major sections
- relative placement of actions
- repeated cards or rows
- where important metadata sits
- what feels primary versus peripheral

Do not try to simulate detailed styling.

## Mobile And Desktop

When the component or page matters on multiple screen sizes:
- say how the option should collapse or stack on mobile
- identify anything that risks overflow, hidden actions, or hierarchy loss
- keep mobile constraints visible during exploration, not as an afterthought

## Handoff

Recommend implementation when:
- the user has selected a direction
- the hierarchy and action placement are clear
- the remaining work is execution

Recommend more shaping when:
- the UI exploration exposes a deeper product-scope or flow ambiguity
- the right UI depends on an unresolved product rule
