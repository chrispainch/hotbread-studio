# Submission Rules

Use one application workspace per role:

```text
applications/
  <year>/
    <company-role-slug>/
      application.json
      tailored-resume.v1.md
      tailored-cover-letter.v1.md
      tailored-resume.v1.html
      tailored-cover-letter.v1.html
```

## Rules

- `data/career-source.json` remains canonical and cross-application
- submitted artifacts live only inside one application workspace
- markdown stays the canonical source after submission
- html is a derived render written beside the markdown source
- preserve the source draft filename in `application.json.submitted_artifacts`
- the skill may finalize only one artifact type at a time
- resume-only applications are valid
- cover-letter-only finalization is valid if a markdown source exists

## Artifact Paths

- Resume:
  - source example: `tailored-resume.v2.md`
  - output example: `tailored-resume.v2.html`
- Cover letter:
  - source example: `tailored-cover-letter.v1.md`
  - output example: `tailored-cover-letter.v1.html`
