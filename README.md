# Hotbread Studio

Hotbread Studio is where Christian Painchaud develops agentic skills for his own use.

This repository currently contains a small set of skill collections organized around practical workflows rather than generic prompts. Each collection lives in its own project folder and exposes skills through `.agents/skills/`.

## Current Projects

### `job-search-skills`

This collection is focused on structured job-search operations: turning career history into reusable source data, tailoring resumes to specific roles, and preserving submitted application artifacts.

- `career-source-intake`: maps existing artifacts such as resumes, CSVs, notes, or exports into a canonical `career-source.json` source of truth.
- `career-source-interview`: enriches or reconstructs career records from memory through guided questioning before saving back to the canonical file.
- `custom-resume`: creates a tailored resume for a specific job posting using evidence from the canonical career source and saves artifacts into an application workspace.
- `application-submit`: converts the final submitted resume or cover letter markdown into HTML and updates the application workspace metadata to reflect what was sent.

At a high level, this project forms a workflow:
`career source -> tailored application artifacts -> submission record`.

### `software-pm-skills`

This collection is aimed at software product and UX work. The skills are arranged around a typical progression from problem definition to solution shaping, interface exploration, and launch planning.

- `problem-framing`: defines the user need, current gap, pain, desired user outcome, and expected organizational value before solution design starts.
- `breadboarding`: maps current-state or target-state workflows into flowchart-ready tables that show screens, affordances, transitions, and technical constraints.
- `solution-shaping`: defines solution boundaries, components, scope, risks, and success criteria without dropping into implementation detail too early.
- `ascii-ui-exploration`: explores screen structure and interaction hierarchy with ASCII concepts once the solution is already shaped.
- `product-launching`: prepares rollout briefs, documentation needs, phased launch plans, and success measurement for a shaped solution.

At a high level, this project forms a workflow:
`frame the problem -> map the flow -> shape the solution -> explore the UI -> prepare the launch`.

## Structure

Current top-level folders:

- `job-search-skills/`
- `software-pm-skills/`

Within each project, skills currently live under:

```text
.agents/skills/<skill-name>/SKILL.md
```

## Summary

The repository currently contains two active agentic skill projects:

1. A job-search system centered on canonical career data and application-specific resume/submission workflows.
2. A software/PM system centered on product thinking, UX flow mapping, solution definition, and launch preparation.
