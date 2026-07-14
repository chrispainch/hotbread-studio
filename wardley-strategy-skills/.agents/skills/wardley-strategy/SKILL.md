---
name: wardley-strategy
description: Use when Codex needs to structure strategy work with Wardley Maps: clarifying user needs, building or critiquing value chains, placing components by evolution, identifying climatic patterns and inertia, separating doctrine from context-specific gameplay, or turning messy strategic discussions into map-driven choices.
---

# Wardley Strategy

Use Wardley Maps as a strategy method, not as decoration. Anchor on user needs, map the landscape, identify climatic forces and inertia, then propose context-specific plays.

Treat the visual Wardley map as a derived view for humans. Treat the primary working artifact as a structured map that another agent can inspect, update, diff, and render.

## Workflow

1. Define the scope.
2. Identify the relevant users and their needs.
3. Build a structured map of components and relationships needed to meet those needs.
4. Position components by evolution: `genesis`, `custom built`, `product`, `commodity / utility`.
5. Surface assumptions, missing components, duplication, and bias.
6. Apply climatic patterns and doctrine.
7. Propose plays, risks, and open uncertainties.
8. Render the structured map into tables, prose, or a visual map only if helpful.

## Operating Rules

- Start with user needs, not business slogans.
- Prefer a structured artifact over a diagram as the source of truth.
- Treat the map as a communication artifact for challenge and learning.
- Separate universal doctrine from context-specific gameplay.
- Avoid deterministic claims. Mapping improves situational awareness; it does not guarantee the right move.
- Challenge whether a component is truly novel or merely marketed as such.
- Watch for inertia caused by past success, sunk cost, org design, or existing business models.
- Keep observations about the landscape separate from choices about what to do.

## Outputs

Produce only what the task needs. Common outputs:

- a canonical structured map in YAML
- a markdown table rendering of that map
- a draft Wardley map in text or visual form
- a critique of an existing strategy through the Wardley lens
- a list of climatic patterns affecting the landscape
- doctrine gaps, duplication, and inertia to address
- context-specific strategic plays with tradeoffs

## Preferred Artifact

Default to the structured schema in [references/structured-map-schema.md](./references/structured-map-schema.md).

Use it as the canonical representation because it:

- makes dependencies explicit
- separates users, components, relationships, patterns, and plays
- supports incremental updates and diffs
- can be rendered into tables or a visual map later

## Rendering Order

Prefer outputs in this order unless the user asks otherwise:

1. `structured YAML`
2. `markdown tables`
3. `visual Wardley map`

## Quick Text Format

When the task is small, use a compact textual structure instead of the full schema:

```text
Users and needs
- User: ...
- Needs: ...

Value chain
- Visible capability -> depends on ...
- Supporting capability -> depends on ...

Evolution
- Component: genesis | custom built | product | commodity

Signals
- Inertia:
- Climatic patterns:
- Doctrine gaps:

Strategic plays
- Play:
- Why here over there:
- Risks:
```

## References

- Read [references/wardley-core.md](./references/wardley-core.md) when you need the mapping mechanics, doctrine, and climatic patterns.
- Read [references/structured-map-schema.md](./references/structured-map-schema.md) when you need the canonical AI-friendly artifact, table format, or rendering guidance.
