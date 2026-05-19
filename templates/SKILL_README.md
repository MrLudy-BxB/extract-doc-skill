# <Skill Display Name> Skill

Source-grounded AI-agent skill for `<API/product/use case>`.

## What This Skill Covers

- `<main topic or endpoint group>`.
- `<main reference area>`.
- `<known supported use case>`.
- Source limitations and ambiguities documented in bundled reports.

## Install

Install this skill from its standalone GitHub repository:

```sh
npx skills add https://github.com/<owner>/<skill-repo>
```

If installing from a local clone of this standalone skill repository, run from the repository root:

```sh
npx skills add .
```

If installing from a repo-local published skills collection, run from the collection repository root:

```sh
npx skills add ./published-skills --skill <skill-name>
```

## Use

Ask questions such as:

- `<example endpoint or feature question>`
- `<example field/schema/concept question>`
- `<example source limitation question>`

## Package Structure

```text
<skill-name>/
├── README.md
├── SKILL.md
├── metadata.json
└── references/
    ├── INDEX.md
    ├── by-topic/
    ├── data/
    └── reports/
```

## Source And Safety Notes

- Source: `<portable source name or public source URL>`.
- No absolute local machine paths are included in this skill.
- Secrets, private tokens, raw credentials, and workflow-only artifacts are not included.
- Known limitations are recorded in `references/reports/validation-report.md`.

## Start Reading

For manual review, start with:

- `SKILL.md`
- `references/INDEX.md`
- `references/reports/validation-report.md`
