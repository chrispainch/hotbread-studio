# Pipeline Rules

Use one application workspace per role:

```text
job-applications/
  <year>/
    <company-role-slug>/
      application.json
      job-posting.md
      requirements.json
      tailored-resume.v1.md
      tailored-resume.v1.html
      tailored-cover-letter.v1.md
      tailored-cover-letter.v1.html
```

## Rules

- `data/career-source.json` remains canonical and cross-application
- each application workspace holds its own current tracking metadata in `application.json`
- tracking updates should be concise, structured, and easy to revise
- preserve resume and cover-letter artifacts; do not rewrite them during tracking updates
- if a user update is ambiguous about the target role, clarify before editing files
- use standard hiring-process language for stages and notes
- broader pipeline updates should be derived from saved workspace metadata rather than invented estimates

## Standard Tracking Fields

- `status`: overall application state
- `stage`: current hiring-process step
- `last_updated`: latest date the record was changed
- `last_interaction_date`: latest meaningful external interaction
- `next_step`: expected next action or waiting state
- `next_step_date`: known date for the next step
- `date_applied`, `date_submitted`, `date_closed`: milestone dates when known
- `activity_log`: concise dated progress entries

## Reporting Guidance

- For state: summarize where the application currently sits
- For progress: summarize recent movement and next likely decision points
- For velocity: summarize how many applications have moved recently or stalled
- For quality: summarize how many roles are advancing versus sitting inactive or closing out
