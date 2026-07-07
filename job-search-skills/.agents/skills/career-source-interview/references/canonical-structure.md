# Canonical Structure

Use one canonical JSON file, usually `data/career-source.json`.

The canonical hierarchy is:

- `organizations[]`
- each organization contains `roles[]`
- each role contains `events[]`

## Canonical Fields

Canonical data should preserve:

- organization identity
- role title and chronology
- event chronology
- raw event narrative:
  - `what`
  - `how`
  - `why`
  - `outcomes`
- `visibility`

Optional structured enrichments may include:

- `type`
- `tags`
- `metrics`
- `stakeholders`
- `tools`
- `source_refs`
- `confidence`

## Rules

- `event` is the atomic evidence unit
- preserve raw text even when structured enrichments are added
- keep uncertainty visible instead of forcing fake precision
- enrich existing canonical records rather than creating separate interview-only note stores
- keep private and public records in the same file
- filter on `visibility` downstream rather than splitting the source of truth
- use `role.location` as the default location field
- use `event.location` only when a specific event needs an override
- do not create a top-level `projects[]` array in v1

## Event Types

Use simple event typing where obvious:

- `transition`
- `achievement`
- `project`
- `milestone`
- `research`
- `leadership`
- `hiring`
- `fundraising`
- `sales`
- `operations`

If uncertain, keep the raw text and choose the least risky type or flag it in review.
