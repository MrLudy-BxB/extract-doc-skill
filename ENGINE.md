# Engine Blueprint

This document explains the core thinking behind the Extract Doc Skill engine and how to recreate the same pattern for other docs-to-skill workflows.

## Purpose

The engine turns messy source documentation into a clean, installable AI-agent skill.

The main idea is not scraping. The main idea is controlled transformation:

```text
source evidence
→ mapped sources
→ cleaned source-equivalent docs
→ categorized references
→ routing indexes
→ final installable skill
```

Each stage has a clear folder, clear responsibility, and clear validation rules.

## Core Thinking

### 1. Separate Evidence From Product

Raw source files are evidence. They are not the final product.

Keep raw inputs, extraction logs, scripts, and notes inside `workflow/`. The final skill should contain only clean, useful, portable files.

This prevents a skill from shipping with:

- private local paths
- raw credentials
- scrape noise
- unfinished drafts
- giant raw source dumps
- temporary workflow artifacts

### 2. Plan Before Extraction

The engine requires a project plan before scraping or converting anything.

The plan defines:

- objective
- allowed sources
- out-of-scope sources
- expected source structure
- final skill name
- categorization strategy
- validation checklist

This prevents uncontrolled collection and keeps the final skill focused.

### 3. Map Sources Before Collecting

Before collecting content, inspect source boundaries.

For example:

- Which docs pages matter?
- Which workbook sheets matter?
- Which API groups exist?
- Which files are source-of-truth?
- Which sources are skipped?
- Which source names are public URLs vs local/private portable names?

Source mapping is the bridge between messy input and traceable output.

### 4. Preserve Meaning While Cleaning

Cleaning means removing noise and formatting content into readable Markdown/JSON without changing meaning.

Do not invent missing behavior.
Do not silently fix ambiguous docs.
Do not turn uncertainty into certainty.

If the source is unclear, record the limitation.

### 5. Categorize By Use, Not By Raw Chunks

A useful skill is not a dump of scraped pages.

References should be organized by how an agent will answer questions:

- endpoint
- feature
- concept
- workflow
- request fields
- response fields
- errors
- authentication
- operational notes

The goal is fast lookup and accurate answers.

### 6. Build Routing Indexes

Agents need compact maps before reading long references.

Useful indexes include:

- topic index
- endpoint index
- concept index
- source index
- skill-reference index
- taxonomy

These indexes help agents route a question to the right reference file.

### 7. Package A Portable Skill

The final skill must work outside the engine repo.

A complete skill package should include:

```text
README.md
SKILL.md
metadata.json
references/INDEX.md
references/by-topic/
references/data/
references/reports/
```

`README.md` is for humans.

`SKILL.md` is for agents.

`references/` contains the actual source-grounded knowledge.

### 8. Validate Before Publishing

Validation checks that the final skill is clean, traceable, and portable.

Check for:

- required files
- source traceability
- no raw workflow files
- no absolute local paths
- no secrets or credentials
- no stale skill names
- indexes pointing to real files
- limitations documented instead of guessed

Publishing is optional and should only happen when explicitly requested.

## Engine Architecture

The engine has four layers.

### Human Layer

Files:

```text
README.md
```

Purpose:

- tell users how to use the repo
- keep the user workflow simple
- point AI agents to `AGENT_KICKSTART.md`

### Agent Layer

Files:

```text
AGENTS.md
AGENT_KICKSTART.md
```

Purpose:

- define agent behavior
- define folder discipline
- define source and safety rules
- route agents to the correct guide

### Guide Layer

Files:

```text
docs/
```

Purpose:

- describe each phase in detail
- keep long instructions out of `README.md`
- make the engine repeatable

Guide phases:

```text
00 big picture
01 project start
02 source mapping
03 raw collection
04 clean and categorize
05 skill building
06 validation and publishing
troubleshooting
```

### Template Layer

Files:

```text
templates/
```

Purpose:

- provide reusable starting points
- enforce consistent output shape
- reduce agent drift

Templates include:

- project plan
- project config
- project README
- skill README
- skill metadata
- skill instructions
- reference index

### Work Product Layer

Files:

```text
projects/
published-skills/
```

Purpose:

- `projects/` holds active extraction work
- `published-skills/` holds optional completed shareable skills

Generated work is ignored by default so the engine repo stays clean.

## Key Techniques

### Folder-Based State Machine

Each folder represents a stage in the pipeline.

```text
workflow/sources/      source maps and boundaries
workflow/raw/          untouched evidence
workflow/cleaned/      cleaned source-equivalent docs
workflow/categorized/  topic/use-case grouped material
workflow/indexes/      lookup maps and routing data
workflow/drafts/       pre-final skill drafts
workflow/reports/      validation and coverage reports
workflow/notes/        uncertainty and decisions
skill/<skill-name>/    final clean package
```

This makes progress inspectable and prevents mixing draft work with final output.

### Source Traceability

Every final reference should trace back to either:

- a public source URL, or
- a portable source name for local/private sources

Final skills should never depend on absolute machine paths.

### Portable Naming

The project folder can describe the extraction job.

The skill name must describe the real product, API, feature, or use case.

This prevents skills with names like:

- `docs-scrape`
- `api-version-2026`
- `source-file-export`
- `workbook-skill`

### Human README vs Agent SKILL.md

A final skill needs two different entrypoints.

`README.md` answers:

- What is this skill?
- How do I install it?
- What can I ask it?
- What is inside the package?

`SKILL.md` answers:

- How should an agent use this skill?
- Which reference should it read first?
- Which indexes route which questions?
- What limitations must it respect?

### Reports As Quality Gates

Reports are not decoration. They prove the package is ready.

Useful reports:

- validation report
- coverage report
- package report

These help future agents and humans know what was checked, what was skipped, and what is still uncertain.

### Optional Publishing

Publishing is separate from building.

A project-local final skill lives in:

```text
projects/<project-id>/skill/<skill-name>/
```

A repo-local shareable copy lives in:

```text
published-skills/skills/<skill-name>/
```

Copy to `published-skills/` only when requested.

## How To Build A Similar Engine

1. Create a short user `README.md`.
2. Create a short agent entrypoint `AGENTS.md`.
3. Create a fuller `AGENT_KICKSTART.md`.
4. Split detailed workflow into phase docs under `docs/`.
5. Create templates for every recurring output.
6. Define strict project and final package folder shapes.
7. Require source mapping before raw collection.
8. Require final validation before publishing.
9. Keep generated project work ignored by default.
10. Treat final output as a portable product, not a work folder.

## Design Principle

The engine should make the right workflow easy and the wrong workflow obvious.

A good run should leave behind:

- clean source maps
- preserved raw evidence
- readable cleaned docs
- useful categorized references
- compact routing indexes
- honest reports
- a portable installable skill

A bad run should be easy to detect because files are in the wrong place, sources are not mapped, names are stale, or validation reports are missing.
