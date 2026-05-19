# Project Engine Blueprint

This file explains how to design a new project engine.

A project engine is a repo that guides an AI agent from messy input to a clean final output.

## The Simple Idea

Every engine needs one clear transformation:

```text
input → process → output
```

Examples:

```text
docs → installable AI skill
research notes → cited report
brand notes → design system
codebase → audit and patch plan
course material → publishable course
```

If you cannot describe the transformation in one line, the engine is not clear yet.

## Core Questions

Before building any engine, answer these:

1. What does the user give the agent?
2. What should the agent produce?
3. What work steps must happen in order?
4. What files are temporary work?
5. What files are final output?
6. What must never be published?
7. How do we know the output is done?

## Standard Engine Shape

Use this structure for most engines:

```text
<engine-repo>/
├── README.md
├── AGENTS.md
├── AGENT_KICKSTART.md
├── ENGINE.md
├── docs/
├── templates/
├── projects/
└── published-output/
```

## File Roles

### `README.md`

For humans.

Keep it short:

```text
clone repo
open with AI agent
tell agent to read AGENT_KICKSTART.md
give source/input
ask agent to create output
```

### `AGENTS.md`

Short instruction file for AI agents.

It should say:

- what this engine does
- what to read first
- required folder shape
- non-negotiable rules

### `AGENT_KICKSTART.md`

Full workflow for AI agents.

It should explain:

- mission
- standard process
- folder rules
- naming rules
- safety rules
- validation rules
- publishing rules

### `ENGINE.md`

Blueprint for engine designers.

It explains how to build another engine using the same pattern.

### `docs/`

Detailed phase guides.

Use docs like:

```text
00-big-picture.md
01-project-start.md
02-source-mapping.md
03-collection.md
04-processing.md
05-final-building.md
06-validation-publishing.md
troubleshooting.md
```

### `templates/`

Reusable file templates.

Good templates reduce agent drift.

Examples:

```text
PROJECT_PLAN.md
project.json
README.md
final-output.md
validation-report.md
```

### `projects/`

Generated project work.

Usually ignored by Git except `.gitkeep`.

### `published-output/`

Optional clean exported output.

Only use this when the user explicitly asks to publish or export.

## Engine Workflow Pattern

Most engines follow this pattern:

```text
plan
→ map input
→ collect raw evidence
→ clean/process
→ organize/categorize
→ build final output
→ validate
→ optionally publish
```

For each step, create a matching folder or report so progress is visible.

## Folder State Pattern

Use folders as workflow states:

```text
workflow/sources/
workflow/raw/
workflow/cleaned/
workflow/categorized/
workflow/indexes/
workflow/drafts/
workflow/reports/
workflow/notes/
final-output/
```

The exact names can change, but the rule stays the same:

```text
messy work stays in workflow/
clean product goes in final-output/
```

## Project Plan

Every engine should require a project plan before work starts.

The plan should define:

- objective
- input sources
- out-of-scope items
- expected source structure
- final output name
- processing strategy
- validation checklist
- open questions

The plan prevents random work.

## Boundary Rule

Always separate work files from final files.

Final output should not contain:

- raw secrets
- private notes
- local machine paths
- temporary scripts
- logs
- unreviewed drafts
- irrelevant source dumps

## Traceability Rule

The final output should be able to answer:

```text
Where did this come from?
```

Traceability can use:

- source URL
- source filename
- source ID
- sheet name
- section name
- evidence note
- report link

Use portable source names for local/private sources.

Do not ship absolute local paths.

## Validation Rule

Every engine needs a definition of done.

Validation should check:

- required final files exist
- names are consistent
- output is portable
- forbidden files are absent
- secrets are absent
- indexes or references point to real files
- uncertainty is documented
- final output matches the plan

## Publishing Rule

Building is not publishing.

Publishing should be optional and explicit.

Recommended pattern:

```text
projects/<project-id>/final-output/
published-output/<output-name>/
```

Only copy to published output when requested.

## How To Create A New Engine

1. Write the one-line transformation.
2. Define the final output folder and required files.
3. Create a short user `README.md`.
4. Create `AGENTS.md`.
5. Create `AGENT_KICKSTART.md`.
6. Create phase docs under `docs/`.
7. Create templates under `templates/`.
8. Create empty `projects/` and `published-output/` folders.
9. Add `.gitignore` rules for generated work.
10. Add validation and publishing rules.

## Good Engine Test

A good engine should pass this test:

```text
Can a user clone the repo, give it to an AI agent, provide source material, and get the same kind of clean output every time?
```

If yes, it is an engine.

If no, it is just notes.
