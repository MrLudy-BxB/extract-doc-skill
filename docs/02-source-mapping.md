# Source Mapping

## Goal

Understand the documentation structure before collecting raw data.

## Source Types To Look For

- Official Markdown or source repository files.
- OpenAPI, AsyncAPI, GraphQL schema, or machine-readable specs.
- `llms.txt` or `llms-full.txt`.
- Sitemap XML.
- Static HTML pages.
- JavaScript-rendered docs.
- API reference pages with hidden JSON data.
- Navigation pages, sidebars, or table-of-contents pages.

## Preferred Source Priority

Use the cleanest official source available:

```text
machine-readable spec
→ official Markdown/source files
→ Markdown export
→ static HTML
→ rendered/dynamic HTML fallback
```

## Multilayer Docs Strategy

If the docs are multilayer:

1. Map the landing pages.
2. Find nav/sidebar/sitemap/index files.
3. Identify product boundaries.
4. Record included and skipped sections.
5. Only then collect raw data.

## Required Outputs

```text
workflow/sources/source-list.md
workflow/sources/skipped-sources.md
workflow/sources/source-map.json
```

At this step, `source-map.json` can be partial. It should become more complete during collection.

## Useful Checks

- Are there multiple docs products mixed together?
- Are docs duplicated across rendered HTML and source Markdown?
- Are some pages marketing-only?
- Are API references generated from OpenAPI?
- Are examples or SDK guides needed for real usage?
- Are there rate limits, auth rules, permissions, errors, or schemas outside endpoint pages?

## Done Checklist

- [ ] Source roots are listed.
- [ ] Crawl/include boundaries are listed.
- [ ] Out-of-scope areas are listed.
- [ ] Best source format is identified.
- [ ] Multilayer navigation is mapped if needed.
- [ ] Unclear sources are recorded.
