---
name: <skill-name>
description: <Use when answering questions about this documentation, API, SDK, or product area.>
metadata:
  short-description: <short display summary>
---

# <Skill Display Name>

Use this skill when the user asks about `<scope>`.

## Lookup Workflow

1. Start with `references/INDEX.md` to choose the smallest useful reference file.
2. For endpoint/API operation questions, inspect `references/data/endpoint-index.json` first when available.
3. For guide, object, schema, event, or concept questions, inspect `references/data/concept-index.json` first when available.
4. For topic-level questions, use `references/data/skill-reference-index.json` or the topic list in `references/INDEX.md`.
5. Load the matching file under `references/by-topic/` for full context.
6. Cite public source URLs when available, or portable source names and bundled reference paths for local/private sources.

## Reference Map

- `references/INDEX.md`: human-readable routing guide.
- `references/data/`: compact lookup and routing indexes when available.
- `references/by-topic/`: grouped Markdown references organized by topic or use case.
- `references/reports/`: validation, coverage, and package reports when available.

## Answering Rules

- Do not invent API behavior, parameters, limits, errors, schemas, or availability absent from the bundled references.
- If bundled references are incomplete or uncertain, say so and check source traceability notes.
- Preserve exact endpoint methods, paths, parameter names, enum values, limits, status codes, and error meanings from the references.
- For implementation help, distinguish required documented behavior from example code choices.
