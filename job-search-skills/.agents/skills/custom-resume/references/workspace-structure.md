# Workspace Structure

Use one workspace folder per application:

```text
applications/
  <year>/
    <company-role-slug>/
      application.json
      job-posting.md
      requirements.json
      tailored-resume.v1.md
      tailored-resume.v2.md
      tailored-cover-letter.v1.md
      tailored-resume.v2.html
      tailored-cover-letter.v1.html
```

## Rules

- `data/career-source.json` remains canonical and cross-application
- application workspaces hold only job-specific inputs and derived outputs
- preserve the original URL in `application.json.source_url`
- use `job-posting.md` as the single local persisted copy of the posting
- use `requirements.json` for derived requirement interpretation
- use markdown as the editable source format for tailored resumes in v1
- the submitted markdown file remains the exact source actually used to apply
- submitted HTML files are derived archives rendered beside the submitted markdown source files

## Suggested Slug Format

Use a stable, readable folder name:

- `company-role-slug`
- examples:
  - `stripe-senior-product-manager`
  - `vercel-product-growth-lead`

Prefer the current year folder based on the application capture date.
