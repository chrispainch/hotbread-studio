# Structured Map Schema

## Purpose

Use this schema as the canonical Wardley artifact for AI work.

Do not treat the visual map as the source of truth. The visual map is a rendering for humans. The structured map is the working model for analysis, revision, and comparison.

## Format Choice

Preferred source format:

- `YAML` for readability and hand-editing

Secondary renderings:

- `markdown tables` for review
- `visual map` for discussion

Use `JSON` only when strict machine interchange is more important than readability.

## Canonical Sections

Represent the map with these top-level sections:

- `scope`
- `users`
- `components`
- `relationships`
- `climatic_patterns`
- `doctrine_assessment`
- `strategic_plays`
- `key_uncertainties`

## YAML Skeleton

```yaml
scope:
  name: ""
  focus: ""
  viewpoint: ""

users:
  - id: ""
    type: ""
    need: ""
    importance: high
    evidence: ""
    gap: ""

components:
  - id: ""
    name: ""
    component_type: capability
    description: ""
    user_visibility: high
    evolution_stage: product
    differentiation: core
    provided_by: us
    inertia_level: medium
    uncertainty: medium
    evidence: ""
    notes: ""

relationships:
  - from: ""
    to: ""
    relation_type: depends_on
    strength: medium
    notes: ""

climatic_patterns:
  - pattern: everything_evolves
    component_ids: [""]
    direction: ""
    impact: ""
    time_horizon: ""
    evidence: ""

doctrine_assessment:
  focus_on_user_needs: ""
  common_language: ""
  transparency: ""
  challenge_assumptions: ""
  remove_duplication_and_bias: ""

strategic_plays:
  - id: ""
    title: ""
    target_component_ids: [""]
    goal: ""
    rationale: ""
    expected_benefit: ""
    risks: []
    doctrine_alignment: ""
    horizon: ""

key_uncertainties:
  - ""
```

## Component Table Design

If rendering the `components` section as a table, use these columns:

- `id`
- `name`
- `component_type`
- `user_visibility`
- `evolution_stage`
- `differentiation`
- `provided_by`
- `inertia_level`
- `uncertainty`
- `notes`

Recommended enums:

- `component_type`: `user_need`, `capability`, `activity`, `practice`, `data`, `knowledge`
- `user_visibility`: `high`, `medium`, `low`
- `evolution_stage`: `genesis`, `custom_built`, `product`, `commodity_utility`
- `differentiation`: `core`, `supporting`, `commodity`
- `provided_by`: `us`, `partner`, `market`, `unknown`
- `inertia_level`: `low`, `medium`, `high`
- `uncertainty`: `low`, `medium`, `high`

## Relationship Table Design

Keep relationships separate from components. Do not bury dependency lists in prose when the map is large.

Use these columns:

- `from`
- `to`
- `relation_type`
- `strength`
- `notes`

Recommended `relation_type` values:

- `depends_on`
- `enables`
- `constrains`
- `replaces`
- `flows_to`

## Climatic Pattern Table Design

Use these columns:

- `pattern`
- `component_ids`
- `direction`
- `impact`
- `time_horizon`
- `evidence`

Useful pattern names:

- `everything_evolves`
- `characteristics_change`
- `no_one_size_fits_all`
- `efficiency_enables_innovation`
- `higher_order_systems_create_value`
- `no_choice_on_evolution`
- `past_success_breeds_inertia`

## Strategic Play Table Design

Keep plays separate from observations about the landscape.

Use these columns:

- `id`
- `title`
- `target_component_ids`
- `goal`
- `rationale`
- `expected_benefit`
- `risks`
- `doctrine_alignment`
- `horizon`

## Rendering Rules

When converting the structured map to markdown tables:

- render `users`, `components`, `relationships`, and `strategic_plays` as separate tables
- keep long explanations in short `notes` fields or adjacent prose
- do not merge doctrine assessment into the component table
- do not merge strategic plays into the relationship table

When converting the structured map to a visual Wardley map:

- use `users` as the anchor
- map `user_visibility` to vertical placement
- map `evolution_stage` to horizontal placement
- use `relationships` to draw dependency lines
- use `climatic_patterns` and `inertia_level` as annotations, not primary geometry

## Alternative Representations

Use these only when they fit the task better than the canonical schema.

### Graph Model

Best for larger landscapes or automated traversal.

Good options:

- node-edge JSON
- Graphviz DOT
- Mermaid graph

### DSL

Best when you need a compact, strict text format.

Example:

```text
user public_customer needs reliable_photo_storage
component photo_storage type=capability visibility=high evolution=product
component object_storage type=capability visibility=low evolution=commodity_utility
photo_storage depends_on object_storage
play move_to_utility targets object_storage
```

### Matrix

Best for spreadsheet-heavy collaboration.

Use:

- component rows with attribute columns
- a separate dependency matrix or relationship sheet

### Outline

Best for quick exploratory notes, not as a durable source of truth.

Use only for small problems or early capture before converting to the structured schema.

## Default Agent Behavior

Unless the user asks for a visual map first:

1. build the structured YAML artifact
2. render tables if useful for review
3. render a visual map only if it improves human discussion
