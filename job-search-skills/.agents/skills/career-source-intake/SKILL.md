---
name: career-source-intake
description: Use when the user wants to turn existing career artifacts into the canonical career source-of-truth file. Trigger for pasted CSV, resume text, LinkedIn exports, markdown notes, spreadsheets, or local file paths that should be mapped into structured organizations, roles, and events with review before save.
metadata:
  short-description: Map career artifacts into canonical records
---

# Career Source Intake

Use this skill when the user already has career material in some form and wants it mapped into the canonical JSON source of truth.

## When To Use

Use this skill when the user asks to:
- ingest pasted career data
- read a local file containing career artifacts
- convert a CSV, resume, notes, or LinkedIn-style export into canonical records
- merge a new source into an existing career source file
- bootstrap the source of truth from prior materials

Do not use this skill when the user mainly wants to reconstruct missing details from memory. That belongs to `career-source-interview`.

## First Read

Before acting, read:
- `references/canonical-structure.md`
- `references/career-source.template.json` if the canonical file does not exist yet

## Core Rules

- Default canonical file path: `data/career-source.json`
- If the user gives a different target path, use it
- Preserve source meaning faithfully; do not aggressively normalize on first pass
- Treat `event` as the atomic unit whenever the source supports it
- Keep raw narrative text canonical: `what`, `how`, `why`, `outcomes`
- Keep public and private records in the same canonical file and preserve `visibility`
- Do not write the canonical file until the user has reviewed the proposed mapping
- Show grouping review first, then event review, then save preview
- Ask only minimal clarification questions needed to avoid structural mistakes

## Workflow

1. Identify the source.
- Accept pasted content or a local file path.
- If the user has not provided either, ask for one.

2. Identify the target file.
- Use `data/career-source.json` by default.
- If the file exists, load it and merge into it.
- If it does not exist, start from `references/career-source.template.json`.

3. Map the source into canonical structure.
- Group by `organization -> role -> event`.
- Infer only obvious event types such as `transition`, `achievement`, `project`, or `milestone`.
- Preserve ambiguous details in raw text instead of forcing structure.

4. Review grouping.
- Show the proposed organizations, roles, and chronology before drilling into full event payloads.
- Surface likely risk areas: merged roles, duplicated organizations, missing dates, or chronology conflicts.

5. Review events.
- Show the proposed events with key fields:
  - `date`
  - `title`
  - `type`
  - `visibility`
  - short previews of `what/how/why/outcomes`
- Distinguish user-provided text from inferred fields.

6. Save preview.
- Show exactly what will be written:
  - full new file if creating from scratch
  - merged or updated sections if editing an existing file
- Only write after explicit user approval.

7. Save.
- Write the file with conservative edits.
- Keep IDs stable when source IDs already exist.
- Do not silently delete existing confirmed records.

## Merge Rules

- Prefer appending new events over rewriting existing confirmed events
- If a source clearly refers to an existing event, update only the fields supported by the new source
- If duplicate detection is uncertain, flag it in review instead of deciding silently
- Preserve prior confirmed structured enrichments unless the new source clearly contradicts them

## Stopping Condition

This skill is done when:
- the source has been mapped into the canonical structure
- the user has reviewed the proposed grouping and event records
- the canonical file has been saved, or the user explicitly declines to save

## Handoff

Recommend `career-source-interview` when:
- imported records are too thin for downstream use
- important roles or projects are missing from the source artifacts
- the user wants to deepen metrics, decisions, stakeholders, or story detail from memory
