---
name: job-pipeline-tracking
description: >-
  Use when the user is mentioning progress, status changes, or interview steps
  for a specific job application and wants the application workspace metadata
  kept current or wants a concise update on overall pipeline progress.
metadata:
  short-description: Track job application progress and pipeline health
---

# Job Pipeline Tracking

Use this skill when the user is discussing progress for one specific job application or wants a concise view of the broader job search pipeline.

## When To Use

Use this skill when the user asks to:
- update an application after applying, hearing back, scheduling, interviewing, or closing the process
- record progress for a role after a recruiter screen, hiring manager call, panel, take-home, onsite, offer, rejection, or withdrawal
- keep `application.json` current after new information arrives
- summarize current pipeline state across saved application workspaces
- report general pipeline progress, velocity, quality, or stage distribution

If it is unclear which job the user means, clarify before updating any workspace.

Do not use this skill to:
- draft or improve resume or cover-letter content
- mutate `data/career-source.json`
- invent progress updates the user did not provide

## First Read

Before acting, read:
- `references/pipeline-rules.md`
- `references/application.template.json`

## Core Rules

- Operate only inside `job-applications/<year>/<company-role-slug>/`
- Update the existing application workspace rather than creating duplicate tracking records
- Keep `application.json` concise, current, and structured
- If the target application is ambiguous, ask a short clarifying question before writing
- Preserve source artifacts and derived resume outputs; this skill updates tracking metadata, not resume content
- Prefer standard, plain hiring-process vocabulary
- Record what changed, when it changed, and what the likely next step is when known
- Pipeline summaries should stay concise and grounded in saved workspace data

## Workflow

1. Identify the target scope.
- If the user refers to one company or one role clearly, use that workspace.
- If the user is asking about overall progress, inspect all saved application workspaces.
- If multiple workspaces could match, require clarification before updating files.

2. Read current tracking data.
- Load the target `application.json` file or all application files in scope.
- Preserve existing values unless the user provided a clear update.

3. Interpret the update.
- Normalize the current stage, status, and next step from the user's update.
- Capture notable milestones such as applied, recruiter screen, interview rounds, offer, rejection, withdrawal, or stalled follow-up.
- When the user asks for pipeline health, summarize stage mix, recent movement, and likely bottlenecks from saved data.

4. Update `application.json`.
- Keep `status`, `stage`, `last_updated`, and `last_interaction_date` current.
- Update `date_applied`, `date_submitted`, `date_closed`, or other milestone dates only when supported.
- Update `next_step` and `next_step_date` when the user mentions them.
- Append a concise entry to `activity_log` for meaningful changes.
- Keep `submitted_artifacts` intact unless the user explicitly changes what was used.

5. Report the result.
- For a single application, show the updated company, role, status, stage, and next step.
- For broader pipeline requests, summarize current counts, momentum, and notable risks or gaps in concise standard language.

## File Rules

- `application.json` is the source of truth for per-application tracking metadata
- `status` should stay concise and current: examples include `draft`, `applied`, `in_progress`, `submitted`, `offer`, `rejected`, `withdrawn`, `closed`
- `stage` should describe the current process step in plain hiring-process language
- `activity_log` should contain short dated entries, newest last
- pipeline summaries may be reported from workspace data without creating extra files unless the user asks for one

## Stopping Condition

This skill is done when:
- the correct application workspace has been identified, or ambiguity has been surfaced to the user
- `application.json` accurately reflects the latest known progress for the targeted role
- the user has a concise update on the relevant application or the broader pipeline

## Handoff

Recommend `custom-resume` when:
- the role still needs a tailored resume or revised resume content

Recommend future cover-letter generation work when:
- the application needs a cover letter that does not yet exist
