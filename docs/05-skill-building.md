# Skill Building

## Goal

Create a clean draft and final skill package from categorized workflow material.

## Required Workflow Outputs

```text
workflow/drafts/
workflow/indexes/
workflow/reports/skill-draft-report.md
```

## Required Final Skill Outputs

```text
skill/<skill-name>/
├── README.md
├── SKILL.md
├── metadata.json
└── references/
    ├── INDEX.md
    ├── by-topic/
    ├── data/
    └── reports/
```

Minimum installable skill requirement:

```text
SKILL.md
```

Recommended documentation skill package:

```text
skill/<skill-name>/
├── README.md
├── SKILL.md
├── metadata.json
└── references/
    ├── INDEX.md
    ├── by-topic/
    ├── data/
    │   ├── source-index.json
    │   ├── topic-index.json
    │   ├── skill-reference-index.json
    │   ├── endpoint-index.json
    │   ├── concept-index.json
    │   └── taxonomy.json
    └── reports/
        ├── validation-report.md
        ├── coverage-report.md
        └── skill-package-report.md
```

## Build Order

1. Build compact indexes under `workflow/indexes/`.
2. Draft reference files under `workflow/drafts/`.
3. Confirm `skill-name` reflects the real API/product/use case, not the source file name.
4. Check the skill and skill README templates.
5. Create final files under `skill/<skill-name>/`.
6. Copy only clean, useful references and reports into final skill.

Package by copying:
- `templates/SKILL_README.md` content adapted to `README.md`.
- `workflow/drafts/INDEX.md` or the approved reference index to `references/INDEX.md`.
- Final topic docs to `references/by-topic/`.
- Routing and lookup indexes to `references/data/`.
- Validation, coverage, and package reports to `references/reports/`.

Before packaging, confirm `skill-name` is final. If the user changes the name, update every package artifact before copying:

- Final folder path.
- `README.md` install and package paths.
- `SKILL.md` frontmatter.
- `metadata.json`.
- `references/INDEX.md`.
- `references/data/source-index.json`.
- `references/reports/skill-package-report.md`.

Do not keep an old final skill folder with the previous name as another current skill.

## `README.md` Rules

Every final skill package should include a root `README.md` for users browsing a standalone GitHub skill repository.

It should include:

- What the skill covers.
- Install command for a standalone GitHub repository.
- Install command for a local clone.
- Install command for a repo-local `published-skills/` collection when applicable.
- Example user questions.
- Package structure.
- Source and safety notes.
- Pointers to `SKILL.md`, `references/INDEX.md`, and validation reports.

Do not include absolute local machine paths, raw credentials, workflow logs, or private source details in the skill README.

## `SKILL.md` Rules

`SKILL.md` should stay small and procedural.

Required YAML frontmatter:

```yaml
---
name: <skill-name>
description: <what this skill does and when to use it>
---
```

Optional frontmatter metadata:

```yaml
metadata:
  short-description: <short display summary>
```

It should tell the agent:

- When to use the skill.
- Start with `references/INDEX.md`.
- For endpoint/API operation questions, inspect `references/data/endpoint-index.json` first when available.
- For guide, object, schema, event, or concept questions, inspect `references/data/concept-index.json` first when available.
- Use `references/data/skill-reference-index.json` or `references/INDEX.md` to route topic-level questions.
- Load `references/by-topic/` files for full context.
- Cite public source URLs when source-grounded answers are needed.
- For local/private files, cite a portable source name and bundled reference path instead of an absolute local machine path.
- Do not invent behavior absent from bundled references.
- If references disagree or are incomplete, say what is unresolved and cite the closest source.

Useful `SKILL.md` sections:

- `Lookup Workflow`
- `Reference Map`
- `Answering Rules`

## `metadata.json` Rules

Recommended fields:

```json
{
  "name": "<skill-name>",
  "displayName": "<Skill Display Name>",
  "description": "<source-grounded skill description>",
  "version": "0.1.0",
  "generatedAt": "<ISO timestamp>",
  "license": "<source/licensing note>",
  "entrypoint": "SKILL.md"
}
```

Use `metadata.json` for package-level metadata. Use `SKILL.md` for agent behavior.

## Reference Rules

Final references should be topic/use-case oriented, not arbitrary raw chunks.

Each major reference should include source traceability, such as:

- Public source URLs when available.
- Portable source names for local/private files.
- Related source ids.
- Known limitations.
- Last collection date if known.

Each major topic reference should include a source traceability section or source records table. This lets the skill answer source disputes by tracing:

```text
final reference
→ categorized workflow record
→ cleaned source-equivalent file
→ raw evidence
→ public source URL
```

## Reference Index Rules

`references/INDEX.md` is the human-readable entry point.

It should include:

- What is included.
- Lookup order.
- Directory map.
- Topic list with file paths.
- Count of records/files when available.
- Source traceability notes.
- Known limitations.

Use paths relative to `references/` in the final package, such as:

```text
by-topic/auth/oauth.md
data/endpoint-index.json
reports/validation-report.md
```

Avoid pointing final skill users to `workflow/` paths unless the project intentionally exposes audit-only source lineage elsewhere.

Do not include absolute local paths such as `/Users/...`, `/Volumes/...`, or `file:///...` in final or published skill files.

## Real Skill Validation

Before calling the skill final, check:

- Required files exist: `SKILL.md`, `metadata.json`, `references/INDEX.md`.
- Recommended indexes exist when applicable: `endpoint-index.json`, `concept-index.json`, `skill-reference-index.json`, `topic-index.json`, `source-index.json`, `taxonomy.json`.
- Topic reference files listed in the index actually exist.
- Index records route to existing topic files.
- Public source URLs are available for citation when the source is public.
- Local/private sources are represented by portable source names, not absolute machine paths.
- Validation and coverage reports are copied into `references/reports/`.
- No raw sources, logs, temporary files, or private notes are copied into the final skill.
- `skill-package-report.md` matches the actual final skill name and path.
- Only one current final skill folder exists under `projects/<project-id>/skill/`.

## Smoke Test Expectations

After packaging, test at least:

- One endpoint/API operation lookup.
- One concept/object/schema/guide lookup.
- One topic navigation lookup.
- One source citation or source-dispute lookup.

## Done Checklist

- [ ] Draft skill material exists under `workflow/drafts/`.
- [ ] `skill-name` is based on the real API/product/use case, not source filename or project id.
- [ ] Final skill exists under `skill/<skill-name>/`.
- [ ] `SKILL.md` has required frontmatter.
- [ ] `metadata.json` exists with package metadata.
- [ ] `references/INDEX.md` is the entry point.
- [ ] `references/data/` contains useful routing indexes.
- [ ] Topic references are organized for agent use.
- [ ] Topic references preserve source traceability.
- [ ] Validation, coverage, and package reports are present when available.
- [ ] Workflow-only files are not copied into final skill.
- [ ] No stale duplicate skill folder remains as a current final skill.
