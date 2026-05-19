# Clean And Categorize

## Goal

Turn raw evidence into usable working references without changing source meaning.

## Required Outputs

```text
workflow/cleaned/
workflow/categorized/
workflow/indexes/
workflow/reports/clean-categorize-report.md
```

## Cleaning Rules

- Remove navigation clutter, duplicated page chrome, hidden UI noise, and irrelevant boilerplate.
- Preserve endpoint paths, methods, parameters, enum values, schemas, limits, errors, permissions, and examples exactly.
- Repair obvious Markdown, table, heading, and code block formatting only when meaning is preserved.
- Do not summarize or invent missing behavior.
- Attach source metadata to cleaned files when possible.

## Categorization Rules

Categorize by what helps an agent answer questions:

- User task.
- API category.
- Endpoint group.
- Product feature.
- Auth or permission model.
- Object/schema/event type.
- Error handling or limits.
- SDK/tooling area.

Prefer deterministic rules before loose keyword guesses:

- Source path.
- Page title.
- API tag.
- Endpoint path prefix.
- Heading hierarchy.
- Official nav group.

## Indexes To Consider

```text
workflow/indexes/source-index.json
workflow/indexes/topic-index.json
workflow/indexes/endpoint-index.json
workflow/indexes/concept-index.json
```

Only create indexes that are useful for the project.

## Done Checklist

- [ ] Cleaned docs exist for useful raw sources.
- [ ] Categorized docs are grouped by useful topics.
- [ ] Source references are preserved.
- [ ] Endpoint/concept/schema indexes exist if relevant.
- [ ] Uncategorized or uncertain content is reported.
