# Troubleshooting

## Dynamic Docs

If content is rendered by JavaScript:

- Look for source Markdown, OpenAPI specs, bundled JSON, `llms.txt`, or GitHub source.
- Use sitemap/navigation pages to discover URLs.
- If automated fetch does not expose content, record the issue and consider browser-assisted extraction.

## Huge Docs

If docs are too large:

- Map first, collect second.
- Split by product, API category, or nav group.
- Use deterministic source ids.
- Process one area at a time.

## Duplicate Sources

If the same content exists in multiple formats:

- Keep raw evidence if useful.
- Prefer machine-readable specs, official Markdown, or source files for cleaned output.
- Record which source type was selected and why.

## Mixed Product Docs

If one site includes many products:

- Define allowed and denied boundaries in `PROJECT_PLAN.md` and `config/project.json`.
- Record skipped sections.
- Ask the user before expanding scope.

## Conflicting Information

If sources disagree:

- Prefer official/current docs over examples, blogs, or old pages.
- Record the conflict in `workflow/reports/`.
- Do not silently merge conflicting behavior.

## Weak OpenAPI Specs

If an OpenAPI spec lacks descriptions:

- Use the spec for paths, methods, parameters, schemas, and response shapes.
- Use guides/examples for usage context.
- Keep exact spec-derived facts separate from explanatory prose.

## No Clear Taxonomy

If docs have no useful categories:

- Start from user tasks.
- Then group by API path prefixes, official nav headings, object types, or lifecycle stages.
- Record the chosen taxonomy in the project plan.

## When To Ask The User

Ask when:

- Sources are private or gated.
- Product scope is ambiguous.
- Multiple official versions exist.
- The final skill should be split into multiple skills.
- Publishing target is unclear.
