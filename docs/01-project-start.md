# Project Start

## Goal

Start a docs-to-skill project safely before any collection or extraction happens.

## Required Outputs

```text
projects/<project-id>/
├── PROJECT_PLAN.md
├── README.md
├── config/
│   └── project.json
├── workflow/
└── skill/
```

## Choose Names

- `project-id`: stable lowercase workspace folder name. It may describe the source or extraction job, such as `billing-api-docs`.
- `skill-name`: installable skill name based on the real API, product, feature, or use case, such as `billing-api`.
- `displayName`: human-readable product or API name.

Do not choose `skill-name` from:

- Source file names.
- Workbook filenames.
- Temporary project ids.
- Scrape job names.
- Version-only labels.

If the source filename is vague but the docs reveal a clearer API/product name, update the plan before creating the final skill.

## Fill The Plan First

Use `templates/PROJECT_PLAN.md`.

The plan must define:

- Objective.
- Final skill name.
- Allowed sources.
- Out-of-scope sources.
- Expected source structure.
- Collection strategy.
- Categorization strategy.
- Validation checklist.
- Open questions.

## Directory Creation Checklist

- [ ] Create `PROJECT_PLAN.md`.
- [ ] Create `README.md`.
- [ ] Create `config/project.json`.
- [ ] Create `workflow/sources/`.
- [ ] Create `workflow/raw/`.
- [ ] Create `workflow/cleaned/`.
- [ ] Create `workflow/categorized/`.
- [ ] Create `workflow/indexes/`.
- [ ] Create `workflow/drafts/`.
- [ ] Create `workflow/reports/`.
- [ ] Create `workflow/notes/`.
- [ ] Create `skill/`.

## Do Not

- Do not begin scraping before the plan exists.
- Do not use one project folder for multiple unrelated APIs.
- Do not guess scope if the source boundaries are unclear.
- Do not publish to `published-skills/` unless the user explicitly asks for a repo-local shareable copy.
