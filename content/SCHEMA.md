---
title: Schema
publish: false
updated: 2026-07-13
---

# Schema

## Scope

Agentic AI: agents, tools, planning, memory, orchestration, evaluation,
safety, frameworks, products, and research.

## Folders

- `raw/` — source records
- `entities/` — people, organizations, products, and frameworks
- `concepts/` — ideas and techniques
- `comparisons/` — comparisons
- `queries/` — open questions
- `_meta/` — optional templates and detailed guidance

## Frontmatter

```yaml
---
title:
type: source | entity | concept | comparison | query
tags: []
sources: []
updated: YYYY-MM-DD
publish: false
---
```

Source records also include `source_url`, `accessed`, and
`redistribution: public-domain | licensed-copy | link-summary-only`.

## Rules

- Use lowercase hyphenated filenames.
- Cite sources for factual claims.
- Label wiki inference as analysis.
- Preserve unresolved contradictions.
- Unknown copyright licenses use `link-summary-only`.
- Only user-approved pages may use the Boolean `publish: true`.
- Add pages to `index.md` and append actions to `log.md`.
