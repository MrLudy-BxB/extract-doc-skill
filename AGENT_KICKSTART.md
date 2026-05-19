# Agent Kickstart

This file is the longer AI-agent operating guide for the Extract Doc Skill engine.

For the short authoritative entrypoint, read `AGENTS.md` first.

## Agent Mission

Turn documentation, specs, workbooks, or source files into a clean, source-grounded, installable skill.

The final skill should be useful from its own folder or standalone GitHub repository. It should not depend on workflow files or local machine paths.

## Standard Flow

```text
1. Read AGENTS.md.
2. Read the guide under docs/ that matches the current phase.
3. Create or update projects/<project-id>/PROJECT_PLAN.md.
4. Map source boundaries before collecting raw evidence.
5. Keep all messy work under projects/<project-id>/workflow/.
6. Build final skill under projects/<project-id>/skill/<skill-name>/.
7. Validate package structure, source traceability, and safety.
8. Copy to published-skills/ only if the user explicitly asks.
```

## Phase Guides

- `docs/00-big-picture.md`: mental model and separation rules.
- `docs/01-project-start.md`: project setup, naming, and plan.
- `docs/02-source-mapping.md`: source inspection and boundary mapping.
- `docs/03-raw-collection.md`: raw evidence and source maps.
- `docs/04-clean-categorize.md`: cleaned docs, categorized references, and indexes.
- `docs/05-skill-building.md`: final skill packaging.
- `docs/06-validation-publishing.md`: validation, publishing, and smoke tests.
- `docs/troubleshooting.md`: common extraction problems.

## Required Project Shape

```text
projects/<project-id>/
├── PROJECT_PLAN.md
├── README.md
├── config/
│   └── project.json
├── workflow/
│   ├── sources/
│   ├── raw/
│   ├── cleaned/
│   ├── categorized/
│   ├── indexes/
│   ├── drafts/
│   ├── reports/
│   └── notes/
└── skill/
    └── <skill-name>/
        ├── README.md
        ├── SKILL.md
        ├── metadata.json
        └── references/
```

## Naming Rules

- Use `project-id` for the workspace/job folder.
- Use `skill-name` for the real API, product, feature, or use case.
- Do not derive `skill-name` only from source filenames, workbook names, scrape jobs, temporary project ids, or version labels.
- If a better API/product name appears during extraction, update the plan and package paths before finalizing.

## Packaging Rules

A documentation skill should include:

```text
README.md
SKILL.md
metadata.json
references/INDEX.md
references/by-topic/
references/data/
references/reports/
```

The root skill `README.md` is for humans browsing GitHub. It should include install commands, example questions, package structure, and source/safety notes.

`SKILL.md` is for agents. Keep it short and procedural.

## Source And Safety Rules

- Raw files are evidence and stay in `workflow/raw/`.
- Final skills must not contain raw sources, logs, temporary files, private notes, or workflow junk.
- Final and published skills must not contain absolute local paths such as `/Users/...`, `/Volumes/...`, or `file:///...`.
- Use public source URLs when available.
- Use portable source names for local/private sources.
- Redact credentials, tokens, secrets, and private headers from final references.
- Record uncertainty instead of guessing.

## Publishing Rules

`published-skills/` is optional repo-local export space.

Only copy a skill there when the user explicitly asks for a repo-local shareable copy.

Before publishing, verify:

- Validation report exists.
- Coverage report exists or coverage notes are documented.
- Root skill `README.md` exists and has install instructions.
- `SKILL.md`, `metadata.json`, indexes, and reports all use the same final `skill-name`.
- No stale duplicate skill folder exists under `projects/<project-id>/skill/`.
- No absolute local paths or raw credentials appear in final/published files.
