# <Skill Display Name> Reference Index

This is the skill-facing entry point. Use it to choose the smallest useful reference file before loading detailed docs.

## Scope

Describe what this skill covers.

## What Is Included

- `<count>` endpoint/API operation records in `data/endpoint-index.json` if applicable.
- `<count>` concept/object/schema/guide records in `data/concept-index.json` if applicable.
- `<count>` topic reference files under `by-topic/`.
- `<count>` source records covered by the organized references.

## How To Navigate

1. For endpoint/API operation questions, use `data/endpoint-index.json` first when available.
2. For guide, object, schema, event, or concept questions, use `data/concept-index.json` first when available.
3. For topic-level questions, use `data/skill-reference-index.json` or the topic list below.
4. Open only the relevant file under `by-topic/` for full context.
5. For source disputes, use source records in topic files and `data/source-index.json` when available.

## Directory Map

- `data/source-index.json`: maps references to public source URLs or portable source names.
- `data/topic-index.json`: maps topics to reference files.
- `data/skill-reference-index.json`: machine-readable routing guide.
- `data/endpoint-index.json`: optional endpoint/API operation lookup.
- `data/concept-index.json`: optional concept/object/schema/guide lookup.
- `data/taxonomy.json`: topic taxonomy when available.
- `by-topic/`: grouped reference docs intended for skill loading.
- `reports/`: validation, coverage, and package reports.

## Topic References

### <Topic Name>

Describe what this topic covers.

Files: `<count>`. Source records: `<count>`.

- `by-topic/<topic>/<file>.md`: `<reference title>` (`<count>` source records)

## Source Traceability

References should preserve public source URLs when available, or portable source names for local/private files, plus known limitations. Topic files should include source records or source links sufficient to trace answers back to original documentation.

## Known Limitations

- 
