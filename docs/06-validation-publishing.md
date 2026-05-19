# Validation And Publishing

## Goal

Prove the skill is complete, source-grounded, cleanly packaged, and ready to share.

## Required Outputs

```text
workflow/reports/validation-report.md
workflow/reports/coverage-report.md
skill/<skill-name>/
published-skills/skills/<skill-name>/ optional repo-local export
```

## Validation Checks

Check coverage layer by layer:

- Approved sources are collected or explained.
- Raw files map to public URLs or portable source names.
- Cleaned files map to raw files.
- Categorized files cover cleaned files or explain exclusions.
- Indexes cover final references.
- Final references cover important categories.
- Root `README.md` explains install, usage, package structure, and source/safety notes.
- `SKILL.md` points to `references/INDEX.md`.
- `skill-name` reflects the real API/product/use case, not source filename, temporary project id, or extraction job name.
- Skill name is consistent across folder name, `SKILL.md`, `metadata.json`, indexes, and reports.
- Final and published files do not contain absolute local machine paths.
- No raw, logs, temporary files, or private notes leaked into final skill.

## Skill Structure Check

Minimum installable skill:

```text
SKILL.md
```

Recommended documentation skill package:

```text
README.md
SKILL.md
metadata.json
references/INDEX.md
references/by-topic/
references/data/
references/reports/
```

Recommended data files when useful:

```text
references/data/source-index.json
references/data/topic-index.json
references/data/skill-reference-index.json
references/data/endpoint-index.json
references/data/concept-index.json
references/data/taxonomy.json
```

Recommended reports:

```text
references/reports/validation-report.md
references/reports/coverage-report.md
references/reports/skill-package-report.md
```

## Publishing Rules

Only publish or copy a skill after validation passes, known issues are documented, and the user explicitly asks for a repo-local shareable copy.

`published-skills/` is optional. Use it only when the user wants this repository to contain a local collection of completed skills. Do not make a generated skill depend on this path.

Before copying, verify there is only one current final skill folder under `projects/<project-id>/skill/`. Do not publish from stale renamed folders.

Copy from:

```text
projects/<project-id>/skill/<skill-name>/
```

To:

```text
published-skills/skills/<skill-name>/
```

## Smoke Test Ideas

Ask the skill to answer:

- One install/readme question.
- One endpoint/API operation question.
- One concept/setup/auth question.
- One source citation question.
- One topic navigation question.

## Done Checklist

- [ ] Validation report exists.
- [ ] Coverage report exists.
- [ ] Package report exists when packaging is complete.
- [ ] Final skill structure is valid.
- [ ] Root `README.md` exists and is correct for standalone GitHub use.
- [ ] `skill-name` is product/API/use-case based.
- [ ] `references/INDEX.md` routes to real topic files.
- [ ] `references/data/` indexes route to real references when present.
- [ ] Skill name and package path are consistent in all final files.
- [ ] No absolute local machine paths appear in final or published files.
- [ ] Source traceability is preserved.
- [ ] Known uncertainty is documented.
- [ ] Published copy exists only if requested and contains only clean skill files.
