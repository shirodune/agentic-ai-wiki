---
title: LLM Wiki
type: source
tags: [agents, knowledge, memory, research]
sources: []
updated: 2026-07-14
publish: true
source_url: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
accessed: 2026-07-14
redistribution: link-summary-only
---

# LLM Wiki

## Source details

- **Author:** Andrej Karpathy
- **Created:** April 4, 2026
- **Original:** [GitHub Gist](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
- **Source type:** Conceptual design note

## Original summary

Karpathy proposes the **LLM Wiki** as a persistent, incrementally maintained knowledge base between a user and raw sources. Unlike query-time retrieval workflows that repeatedly reconstruct an answer from document chunks, the pattern has an LLM integrate each source into an evolving set of interlinked Markdown pages.

The source describes three layers:

1. **Raw sources** are the curated, immutable source of truth.
2. **The wiki** contains LLM-generated summaries, entities, concepts, comparisons, and synthesis.
3. **The schema** tells the agent how to structure and maintain the wiki.

Three recurring operations drive the system. **Ingest** incorporates a source across relevant pages; **query** synthesizes from the compiled wiki and can file valuable answers back into it; **lint** checks contradictions, staleness, orphans, missing links, and research gaps.

An `index.md` provides a content-oriented catalog, while an append-only `log.md` records the wiki's evolution. The note presents Obsidian as one possible browsing environment and Git as a source of history and collaboration.

The human curates sources, directs analysis, and asks questions. The LLM performs summarization, cross-referencing, filing, and consistency maintenance.

## Evidence and limitations

This is the primary conceptual source for the LLM Wiki pattern and for the workflow practiced by this repository. It is an idea file rather than a controlled evaluation or interoperability specification.

The contrast with retrieval-augmented generation is useful but simplified: an LLM Wiki and retrieval can coexist, and a large wiki may still need search or retrieval. The claim that LLM maintenance cost approaches zero omits model cost, review effort, source drift, hallucination, merge conflicts, access control, and governance.

The pattern assumes that agent-generated synthesis and cross-links are checked well enough to avoid compounding mistakes. It does not prescribe a complete provenance, copyright, security, or publication policy; those are local schema decisions.

No explicit redistribution license was identified for the Gist, so this record contains only metadata, an original summary, and links.

## Related pages

- [[concepts/llm-wiki-pattern|LLM Wiki Pattern]]
- [[comparisons/llm-wiki-vs-okf|LLM Wiki Pattern vs OKF]]
- [[concepts/open-knowledge-format|Open Knowledge Format]]
- [[concepts/agent-skills|Agent skills]]
