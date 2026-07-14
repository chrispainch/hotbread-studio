# Job Search Skills

This collection supports a structured job-search workflow built around one durable source of truth for career history and a separate workspace for each application.

## What This Collection Covers

The skills in this folder help with four distinct jobs:

- turning resumes, exports, notes, or spreadsheets into canonical career records
- filling gaps in those records from memory
- tailoring a resume to one specific job posting
- tracking progress for each active application

The intended flow is:

```text
career artifacts or memory
  -> canonical career source
  -> application workspace
  -> tailored resume drafts
  -> application tracking updates
```

## Collection Structure

Skills live under `.agents/skills/<skill-name>/`.

- `career-source-intake/`
- `career-source-interview/`
- `custom-resume/`
- `job-pipeline-tracking/`

Each skill folder contains:

- `SKILL.md`: the operational instructions Codex follows
- `agents/openai.yaml`: agent wiring for the skill
- `references/`: templates, schemas, and supporting guidance

## Shared Data Model

This collection uses two main storage layers:

- `data/career-source.json`: the canonical source of truth for organizations, roles, and events
- `job-applications/<year>/<company-role-slug>/`: one workspace per application, containing artifacts like `application.json`, `job-posting.md`, `requirements.json`, and generated resume drafts

The canonical career source is persistent and reusable across many applications. Application workspaces are derived and role-specific.

## Skill Index

### `career-source-intake`

Maps existing materials into canonical structured records.

Use it when the user has source documents already:

- resume text
- LinkedIn exports
- CSV files
- markdown notes
- spreadsheets
- local files containing career history

### `career-source-interview`

Enriches or reconstructs career evidence through guided questioning.

Use it when the source file exists but is thin, incomplete, or missing specific details such as:

- metrics
- stakeholders
- tools
- decisions
- project outcomes
- missing chronology

### `custom-resume`

Generates a job-specific resume for one target posting using evidence from the canonical career source.

It captures the posting, interprets requirements, selects evidence, and writes editable markdown plus sibling HTML outputs inside the application workspace.

### `job-pipeline-tracking`

Keeps application metadata current after applying, interviewing, receiving a response, or closing the process.

It updates `application.json` and can also summarize the broader pipeline across saved workspaces.

## Working Conventions

- Keep canonical career data and application-specific artifacts separate.
- Do not invent qualifications or retroactively rewrite confirmed history.
- Prefer explicit review before writing source-of-truth files.
- Keep resume outputs derived and regenerable.
- Preserve user-provided facts distinctly from inferred structure or interpretation.

## Typical End-To-End Usage

1. Use `career-source-intake` to import existing history into `data/career-source.json`.
2. Use `career-source-interview` to deepen weak roles, projects, or outcomes.
3. Use `custom-resume` to create a tailored resume for a specific posting.
4. Use `job-pipeline-tracking` to record submission, interviews, and final outcomes.
