# Raw Collection

## Goal

Save untouched source evidence for every approved source.

## Required Outputs

```text
workflow/raw/
workflow/sources/source-map.json
workflow/reports/collection-report.md
```

## Source Map Fields

Each collected source should record:

- Stable id or slug.
- Public source URL when available.
- Portable source name for local/private files.
- Raw fetch URL if different.
- Source type.
- Raw file path.
- Fetch status.
- Content type.
- Collection date.
- Notes or warnings.

## Rules

- Raw files are evidence.
- Do not clean, summarize, or rewrite raw files.
- Keep public citation URLs separate from raw fetch URLs.
- Keep absolute local machine paths only in workflow files when needed for audit; do not copy them into final or published skills.
- Save failed fetches and skipped pages in reports.
- Use deterministic filenames based on source path or canonical URL.
- Respect source boundaries from `PROJECT_PLAN.md` and `project.json`.

## If Direct Collection Fails

Try, in order:

1. Official source repository.
2. Markdown export or `llms.txt`.
3. Sitemap or nav discovery.
4. Static page fetch.
5. Browser-assisted/manual extraction.
6. Ask user if content is gated, private, or unclear.

## Done Checklist

- [ ] Raw files exist for approved sources.
- [ ] `source-map.json` maps raw files to public URLs or portable source names.
- [ ] Collection failures are recorded.
- [ ] Skipped sources have reasons.
- [ ] No cleaned or rewritten content is stored as raw evidence.
