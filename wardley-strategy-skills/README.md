# Wardley Strategy Skills

This collection contains strategy skills based on Wardley Mapping.

## What This Collection Covers

The goal is to turn loose strategic discussion into a structured map of:

- users and their needs
- the value chain required to meet those needs
- the evolutionary position of each component
- climatic patterns, doctrine gaps, and inertia
- context-specific strategic plays

The collection currently contains one skill:

- `wardley-strategy/`

## Collection Structure

Skills live under `.agents/skills/<skill-name>/`.

Each skill folder contains:

- `SKILL.md`: the machine-facing operating instructions
- `agents/openai.yaml`: skill wiring
- `references/`: schema and reference material

## Included Skill

### `wardley-strategy`

Use this skill when the work needs structured strategy analysis instead of generic planning language.

Typical uses:

- building a Wardley map from scratch
- critiquing an existing strategy through a Wardley lens
- clarifying user needs before strategic discussion drifts
- mapping value chains and dependencies
- identifying inertia, duplication, doctrine gaps, and climatic patterns
- proposing context-specific plays with tradeoffs

## Working Conventions

- Start with user needs, not slogans.
- Treat the structured artifact as canonical.
- Use visual maps as derived communication outputs.
- Keep landscape observation separate from strategic choices.
- Avoid deterministic claims; the map improves situational awareness rather than guaranteeing decisions.

## Typical Usage Pattern

1. Define the user and the need.
2. Build the value chain.
3. Place components by evolution.
4. Surface climatic forces, inertia, and doctrine gaps.
5. Propose strategic plays grounded in the mapped context.
