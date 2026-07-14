# Software PM Skills

This collection supports product thinking and UX work from early problem definition through rollout planning.

## What This Collection Covers

The skills in this folder are meant to be used in sequence when the work starts vague and becomes progressively more concrete:

```text
problem framing
  -> workflow mapping
  -> solution shaping
  -> UI exploration
  -> launch planning
```

They are designed to prevent common failure modes:

- jumping into UI before the problem is clear
- shaping a solution before the user need is well defined
- over-specifying implementation too early
- treating launch as an afterthought once code exists

## Collection Structure

Skills live under `.agents/skills/<skill-name>/`.

- `problem-framing/`
- `breadboarding/`
- `solution-shaping/`
- `ascii-ui-exploration/`
- `product-launching/`

Each skill folder contains:

- `SKILL.md`: the machine-facing operating instructions
- `agents/openai.yaml`: skill wiring
- `references/`: templates and supporting docs

## Skill Index

### `problem-framing`

Clarifies the user need, current gap, pain, desired outcome, and expected organizational upside before solution work begins.

Use it when the user is still asking:

- what problem is worth solving
- who is affected
- why it matters
- how painful it is
- whether the opportunity is worth pursuing

### `breadboarding`

Maps current-state or target-state workflows into a flowchart-ready table.

Use it when the main ambiguity is the shape of the workflow:

- screens or states
- affordances
- transitions
- technical handoffs
- broken or missing steps

### `solution-shaping`

Defines the bounded solution before implementation starts.

Use it to document:

- in-scope and out-of-scope behavior
- major components
- risks and constraints
- success criteria
- measurement approach

### `ascii-ui-exploration`

Explores interface options in text after the solution is already shaped.

Use it when the remaining question is:

- hierarchy
- grouping
- action placement
- layout direction
- interaction emphasis

### `product-launching`

Prepares rollout, documentation, enablement, and success measurement for a shaped solution.

Use it when the feature or product direction is defined and the work now needs:

- launch briefs
- rollout phases
- support readiness
- help-doc updates
- launch metrics

## Working Conventions

- Stay at the right altitude for the current phase.
- Use problem artifacts to justify solution work.
- Use flow artifacts to clarify transitions and component boundaries.
- Keep UI exploration focused on hierarchy, not strategy reset.
- Tie launch work back to the intended user and organizational outcomes.

## Typical Usage Pattern

1. Frame the problem and confirm it is worth solving.
2. Breadboard the relevant current or target flow when workflow clarity matters.
3. Shape the solution with clear scope and success measures.
4. Explore the UI only after the solution boundary is stable.
5. Prepare launch materials once the solution is real enough to roll out.
