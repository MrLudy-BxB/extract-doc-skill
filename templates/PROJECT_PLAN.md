# <Project Name> Docs-To-Skill Plan

## Objective

Describe what documentation will become a skill and what the final skill should help agents answer.

## Final Skill Name

`<skill-name>`

Use the real API, product, feature, or use-case name. Do not use a source filename, workbook filename, scrape job name, or temporary project id unless that is also the real product/API name.

## Display Name

`<Skill Display Name>`

## Allowed Sources

List official docs, specs, repositories, pages, or files that may be used.

## Out Of Scope

List docs, products, versions, pages, or sources that should not be collected.

## Expected Source Structure

Describe whether the docs are simple, multilayer, generated, source-backed, OpenAPI-based, or unclear.

## Collection Strategy

Explain how raw sources will be collected and where source maps will be recorded.

## Categorization Strategy

Describe the intended grouping: use case, API area, endpoint category, product feature, schema type, or another taxonomy.

## Final Skill Structure

Describe expected final references, indexes, and reports.

## Workflow Checklist

- [ ] Read `AGENTS.md`.
- [ ] Read `AGENT_KICKSTART.md` if agent workflow details are needed.
- [ ] Read relevant docs under `docs/`.
- [ ] Define allowed sources.
- [ ] Define out-of-scope sources.
- [ ] Map source structure before collection.
- [ ] Confirm final skill name from real API/product/use-case.
- [ ] Collect raw evidence under `workflow/raw/`.
- [ ] Record sources under `workflow/sources/`.
- [ ] Clean or normalize source-equivalent docs under `workflow/cleaned/`.
- [ ] Categorize useful docs under `workflow/categorized/`.
- [ ] Build indexes under `workflow/indexes/`.
- [ ] Draft skill material under `workflow/drafts/`.
- [ ] Create final skill under `skill/<skill-name>/`.
- [ ] Create final skill root `README.md` from `templates/SKILL_README.md`.

## Validation Checklist

- [ ] Raw sources trace to public URLs or portable source names.
- [ ] Skipped or failed sources are documented.
- [ ] Cleaned docs preserve source meaning.
- [ ] Categorized docs cover important source material.
- [ ] Final skill has `SKILL.md`.
- [ ] Final skill has root `README.md` with install and usage instructions.
- [ ] Final skill name is not just a source filename or temporary project id.
- [ ] Final documentation skill has `metadata.json`.
- [ ] Final skill has `references/INDEX.md`.
- [ ] Final skill has useful routing indexes under `references/data/`.
- [ ] Final skill has useful reference files.
- [ ] Final skill has validation, coverage, and package reports when available.
- [ ] Workflow-only files are not in final skill.
- [ ] Uncertainty is recorded instead of guessed.

## Publishing Checklist

- [ ] Validation report exists.
- [ ] Coverage report exists or coverage notes are documented.
- [ ] Package report exists or package notes are documented.
- [ ] User confirmed publishing/export target.
- [ ] Completed skill copied to `published-skills/skills/<skill-name>/` if requested.

## Open Questions

- 
