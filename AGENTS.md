# AGENTS.md

You are working in the Extract Doc Skill engine.

Your job is to turn documentation into a clean, source-grounded, installable skill.

## Start Here

1. Read this file.
2. Read `AGENT_KICKSTART.md` when you need the fuller operating workflow.
3. Read the guide that matches your current step.
4. Create or update `projects/<project-id>/PROJECT_PLAN.md` before scraping or extraction.
5. Keep all work artifacts inside `projects/<project-id>/workflow/`.
6. Put the final skill only inside `projects/<project-id>/skill/<skill-name>/`.
7. Validate source traceability and clean separation before publishing.
8. If the user wants a repo-local shareable copy, copy only completed skills to `published-skills/skills/<skill-name>/`.

## Docs Index

- `docs/00-big-picture.md`: whole engine model, data flow, and separation rules.
- `docs/01-project-start.md`: create a project, plan, config, and folders.
- `docs/02-source-mapping.md`: inspect docs, source types, boundaries, and multilayer navigation.
- `docs/03-raw-collection.md`: collect untouched raw evidence and source maps.
- `docs/04-clean-categorize.md`: clean without changing meaning and categorize by useful topics.
- `docs/05-skill-building.md`: build references, indexes, `SKILL.md`, and final package files.
- `docs/06-validation-publishing.md`: validate, package, publish, and smoke-test.
- `docs/troubleshooting.md`: handle dynamic docs, huge docs, duplicates, weak specs, and ambiguity.
- `AGENT_KICKSTART.md`: longer agent workflow, package rules, safety rules, and publishing rules.

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

## Rules

- Plan before scraping.
- Map sources before collecting raw data.
- Choose `skill-name` from the real API, product, feature, or use case; do not name skills after source files, workbook filenames, scrape jobs, or temporary project ids.
- Raw files are evidence; do not rewrite them.
- Cleaned files must preserve source meaning.
- Categorized files must remain traceable to sources.
- Final references should be topic/use-case oriented, not arbitrary raw chunks.
- Final skill packages should include a root `README.md` with install commands, usage examples, package structure, and source/safety notes.
- Keep public source URLs separate from raw fetch URLs.
- Do not put absolute local machine paths in final or published skills; use source names, public URLs, or bundled reference paths instead.
- If the final skill name changes, update `PROJECT_PLAN.md`, `config/project.json`, `SKILL.md`, `metadata.json`, reference indexes, reports, and package paths before publishing.
- Keep only one current final skill folder under `projects/<project-id>/skill/`; archive or remove stale draft skill folders before publishing.
- Prefer official specs, Markdown, or source files over rendered HTML when available.
- Record skipped sources, warnings, conflicts, and uncertainty in `workflow/reports/` or `workflow/notes/`.
- `published-skills/` is optional repo-local export space, not required for standalone skill use.
- Do not create or update `published-skills/` unless the user explicitly asks for a repo-local shareable copy.
- Do not put raw sources, logs, temporary files, private notes, or workflow junk in final or published skills.
