# Big Picture

## Goal

Use this engine to transform documentation into a clean, source-grounded, installable skill.

The engine gives agents a safe workflow and clear folders. It does not assume every documentation site can be handled the same way.

## Mental Model

```text
source docs
→ workflow/raw evidence
→ workflow/cleaned source-equivalent docs
→ workflow/categorized working references
→ workflow/indexes routing data
→ workflow/drafts skill draft
→ skill/<skill-name>/ final package
→ optional published-skills/skills/<skill-name>/ repo-local shareable copy
```

## Key Separation

- `workflow/`: working area. Raw files, cleaned files, notes, drafts, reports, and indexes belong here.
- `skill/`: final clean package. Only files needed by the installable skill belong here.
- `published-skills/`: optional repo-local export area for completed shareable skills only.

## Source Traceability

Every useful final reference should be traceable back to public source URLs when available, or portable source names for local/private sources, and raw saved evidence when possible.

Carry this information forward:

- Public source URL when available.
- Portable source name for local/private files.
- Raw fetch URL if different.
- Raw file path.
- Cleaned file path.
- Category/topic.
- Known uncertainty.

## What Not To Do

- Do not scrape before creating `PROJECT_PLAN.md`.
- Do not ship arbitrary chunks as final docs.
- Do not hide skipped or failed sources.
- Do not mix multiple unrelated products in one project.
- Do not put workflow files into the final skill.

## Done Checklist

- [ ] Project has a plan.
- [ ] Workflow and final skill are separated.
- [ ] Raw sources or skipped reasons are recorded.
- [ ] Cleaned and categorized docs preserve source meaning.
- [ ] Final skill has an index and references.
- [ ] Final documentation skill has `README.md`, `SKILL.md`, `metadata.json`, and `references/INDEX.md`.
- [ ] Open questions are recorded instead of guessed.
