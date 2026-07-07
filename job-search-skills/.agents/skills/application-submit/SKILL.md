---
name: application-submit
description: >-
  Use when the user has finalized a resume or cover letter markdown file inside
  an application workspace and wants to convert that file to HTML and update
  the application record to reflect submission.
metadata:
  short-description: Convert submitted markdown artifacts to HTML
---

# Application Submit

Use this skill when the user says a resume or cover letter is final and has been submitted for one specific application.

## When To Use

Use this skill when the user asks to:
- submit `@filename` from an application workspace
- convert a final resume markdown file to HTML
- convert a final cover-letter markdown file to HTML
- update an application workspace so it reflects what was actually sent

Do not use this skill to:
- draft or improve resume or cover-letter content
- generate a generic HTML export outside an application workspace
- mutate `data/career-source.json`

## First Read

Before acting, read:
- `references/submission-rules.md`
- `references/application.template.json`

## Core Rules

- Operate only inside `job-applications/<year>/<company-role-slug>/`
- The user's referenced markdown file remains the canonical source
- HTML is a sibling derived artifact created from that markdown file
- Preserve provenance by recording the source markdown filename in `application.json`
- Support partial submission: resume-only or cover-letter-only is valid
- Do not alter the markdown content during submission
- Prefer the exact file the user referenced rather than copying into a new canonical markdown filename

## Workflow

1. Identify the application workspace and source markdown file.
- The source must be an existing markdown file inside the workspace.
- The usual user prompt shape is: `I want to submit "@filename" in my application.`

2. Infer or confirm the artifact type.
- Resume files update the `resume` entry in `application.json.submitted_artifacts`.
- Cover-letter files update the `cover_letter` entry in `application.json.submitted_artifacts`.
- If the filename is ambiguous, require explicit user direction.

3. Render HTML directly from the markdown file.
- Read the markdown file content.
- Write a sibling `.html` file with the same basename.
- Preserve the document meaning and structure while using simple readable HTML.

4. Update `application.json`.
- Set `status` to `submitted`.
- Set or update `date_submitted`.
- Write `submitted_artifacts` metadata with source and generated HTML paths.

5. Report the result.
- Show the source markdown file used
- Show the generated HTML path
- Show the updated application status

## File Rules

- `<name>_cv_<role>_<company>.vN.md` or another referenced markdown file may be the submitted source
- the generated HTML file should sit beside the markdown source, using the same basename
- example: `christianpainchaud_cv_nesto.v2.md` -> `christianpainchaud_cv_nesto.v2.html`
- example: `christianpainchaud_letter_nesto.v1.md` -> `christianpainchaud_letter_nesto.v1.html`
- `application.json` stores structured submission metadata under `submitted_artifacts`

## Stopping Condition

This skill is done when:
- the referenced markdown source remains intact
- the corresponding HTML artifact exists beside it
- `application.json` reflects submission metadata accurately
- the user can identify exactly which markdown file was submitted

## Handoff

Recommend `custom-resume` when:
- the resume markdown is not final yet
- the selected resume file still needs content changes

Recommend future cover-letter generation work when:
- the cover letter does not yet exist as a markdown artifact
