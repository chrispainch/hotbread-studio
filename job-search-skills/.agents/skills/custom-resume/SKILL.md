---
name: custom-resume
description: >-
  Use when the user wants a tailored resume for a specific job posting. Trigger
  for prompts like "create a resume for this job posting: {url}" or requests to
  save a job posting, interpret its requirements, select relevant evidence from
  `data/career-source.json`, and generate a job-specific resume inside an
  application workspace.
metadata:
  short-description: Create tailored resumes for job postings
---

# Custom Resume

Use this skill when the user wants a tailored resume for one specific job posting.

## When To Use

Use this skill when the user asks to:
- create a resume for a job posting URL
- tailor a resume to a saved application workspace
- capture a job posting locally and generate a derived resume draft
- reinterpret requirements for one application and regenerate the resume
- produce another version of a tailored resume for the same role

Do not use this skill to update the canonical career source file. That belongs to `career-source-intake` and `career-source-interview`.

## First Read

Before acting, read:
- `references/workspace-structure.md`
- `references/application.template.json`
- `references/requirements.template.json`
- `references/resume.template.md`

## Core Rules

- Default canonical career source path: `data/career-source.json`
- Job-specific artifacts live under `job-applications/<year>/<company-role-slug>/`
- The default user input is a job-posting URL
- Preserve the original source URL in `application.json`
- Persist one clean local copy of the posting as `job-posting.md`
- Requirement interpretation is derived application data, not canonical career data
- Tailored resume outputs are derived artifacts and may be regenerated
- Do not mutate `data/career-source.json` as part of resume generation
- Review requirement interpretation before finalizing the resume when the capture is ambiguous or the posting is noisy
- Store resumes in markdown first unless the user explicitly asks for another format
- Do not invent missing qualifications
- If an important requirement is unsupported by the career source, keep it out of the resume and surface that gap clearly
- Optimize for credible evidence selection first, keyword coverage second

## Workflow

1. Identify the target posting.
- Prefer a pasted URL.
- If the user does not provide a URL, accept a saved application workspace or pasted posting text.

2. Load the canonical career source.
- Use `data/career-source.json` by default.
- If the file is missing, stop and tell the user the career source file is required.

3. Create or select the application workspace.
- Use the workspace layout in `references/workspace-structure.md`.
- Save or update:
  - `application.json`
  - `job-posting.md`
  - `requirements.json`

4. Capture the job posting.
- If a URL is provided, fetch the job posting page content and preserve the source URL.
- Save a normalized local copy in `job-posting.md`.
- If capture is incomplete, flag that clearly before generating the resume.

5. Interpret requirements.
- Extract and derive:
  - role title
  - must-haves
  - preferred signals
  - responsibilities
  - tools and technologies
  - soft skills
  - domain and industry language
  - emphasis areas and risks
- Save that derived interpretation in `requirements.json`.
- Keep this interpretation editable and regenerable.

6. Select evidence from the career source.
- Pull the strongest relevant organizations, roles, and events from `data/career-source.json`.
- Compare each important requirement against the career source:
  - if direct evidence exists, prioritize and emphasize it
  - if adjacent but truthful evidence exists, use it carefully
  - if evidence is weak, strengthen phrasing with real impact and context
  - if evidence is missing, do not invent it
- Favor evidence that is credible, role-relevant, and specific.
- Avoid keyword stuffing or claims not anchored in the career source.

7. Generate the tailored resume.
- Start from `references/resume.template.md`.
- Reorder experience so the most relevant evidence appears first.
- Write a tailored summary aligned to the target role.
- Rewrite bullets to match the posting's language and priorities without copying verbatim.
- Strengthen achievements with measurable impact when available.
- Keep the output ATS-friendly: no tables, icons, or decorative structure.
- Write the resume as a derived markdown artifact in the application workspace.
- Default to `tailored-resume.v1.md` for the first draft.
- Use later explicit version numbers for meaningful revisions.

8. Review and save.
- Show the user:
  - the key requirement interpretation
  - the main evidence selected from the career source
  - any important unsupported requirements
  - the generated draft path
- If revising, either overwrite the current draft intentionally or create a new numbered version.
- If the user wants to mark the final version, save `submitted-resume.md`.

## Resume Writing Rules

- Stay anchored to real evidence in `data/career-source.json`
- Prefer relevance over completeness
- Omit strong but irrelevant experience rather than diluting the story
- Align language to the job posting without parroting it mechanically
- Compress evidence into a coherent narrative instead of dumping every matching keyword
- When unsure between two directions, bias toward credibility and specificity
- Use ATS-friendly plain structure
- Prefer explicit accomplishments over generic responsibility statements
- Reorder and rewrite existing evidence before inventing new résumé sections

## File Rules

- `application.json` stores structured metadata about the target role and application
- `job-posting.md` stores the local working copy of the posting
- `requirements.json` stores derived interpretation
- `<name>_cv_<company>_<job>.vN.md` stores generated drafts

## Stopping Condition

This skill is done when:
- the application workspace has the required captured posting artifacts
- `requirements.json` has been created or updated
- a tailored resume draft has been saved in the workspace
- the user has enough output to review, revise, or submit

## Handoff

Recommend `career-source-interview` when:
- the best evidence for the target role is too thin in `data/career-source.json`
- the generated resume reveals missing metrics, stakeholders, or project detail that should be added to the source of truth

Recommend `application-submit` when:
- the resume markdown is final and has been submitted
- the user wants canonical submitted artifacts plus rendered HTML archived in the workspace
