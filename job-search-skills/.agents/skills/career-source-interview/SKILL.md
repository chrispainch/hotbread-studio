---
name: career-source-interview
description: Use when the user wants to deepen, clarify, or add career details from memory into the canonical career source-of-truth file. Trigger for filling gaps after intake, reconstructing missing roles or projects, adding metrics or stakeholders, or turning vague records into stronger event evidence with review before save.
metadata:
  short-description: Enrich career records from memory
---

# Career Source Interview

Use this skill when the user needs to add or deepen career records through guided questioning rather than artifact mapping.

## When To Use

Use this skill when the user asks to:
- fill gaps in the canonical career source file
- deepen a specific role, project cluster, or event set
- recover missing details from memory
- add metrics, stakeholders, tools, decisions, or outcomes
- turn shallow imported records into stronger downstream evidence

Do not use this skill when the main task is converting an existing source document into the canonical format. That belongs to `career-source-intake`.

## First Read

Before acting, read:
- `references/canonical-structure.md`
- `references/career-source.template.json` if the canonical file does not exist yet

## Core Rules

- Default canonical file path: `data/career-source.json`
- If the user gives a different target path, use it
- Prefer bounded interview scopes: one role, one project cluster, one organization, or one gap list at a time
- Establish chronology before asking for deep detail if a record does not exist yet
- Preserve uncertainty instead of forcing false precision
- Keep raw narrative text canonical: `what`, `how`, `why`, `outcomes`
- Ask follow-up questions only where they materially strengthen downstream usefulness
- Do not write the canonical file until the user has reviewed the proposed additions or edits

## Workflow

1. Identify the interview scope.
- Prefer one of:
  - a specific organization
  - a specific role
  - a known event cluster
  - a gap list from the current file
- If the user asks broadly, narrow the scope before proceeding.

2. Identify the target file.
- Use `data/career-source.json` by default.
- If the file exists, read the relevant section before interviewing.
- If it does not exist, start from `references/career-source.template.json` and establish basic chronology first.

3. Conduct bounded questioning.
- Start with missing structural basics:
  - organization
  - role
  - date or date range approximation
  - event title or milestone
- Then deepen only the useful fields:
  - `what`
  - `how`
  - `why`
  - `outcomes`
  - optional `metrics`, `stakeholders`, `tools`, `tags`

4. Mark uncertainty honestly.
- Use approximate dates when needed.
- Keep disputed or fuzzy recollections visible instead of flattening them into asserted facts.

5. Review proposed additions.
- Show the exact records or updates that will be added to the canonical file.
- Distinguish user-provided facts from inferred fields such as event type or tags.

6. Save preview and write.
- Show a readable preview of what will change.
- Only write after explicit user approval.

## Interview Guidance

- Ask short, high-signal questions
- Prefer one missing dimension at a time
- Bias toward evidence that improves downstream customization:
  - business impact
  - scale
  - decision-making
  - tools and methods
  - cross-functional collaboration
  - measurable outcomes
- Stop when the selected scope is strong enough for downstream use; do not keep digging without reason

## Stopping Condition

This skill is done when:
- the selected scope has been enriched enough to be useful downstream
- the user has reviewed the proposed additions or updates
- the canonical file has been saved, or the user explicitly declines to save

## Handoff

Recommend `career-source-intake` when:
- the user has more existing source artifacts to map
- too much valuable detail already exists in documents and should be ingested before more interviewing
