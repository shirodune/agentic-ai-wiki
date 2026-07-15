---
title: Introducing the Open Knowledge Format
type: source
tags: [agents, knowledge, interoperability, protocols]
sources: []
updated: 2026-07-14
publish: true
source_url: https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing
accessed: 2026-07-14
redistribution: link-summary-only
---

# Introducing the Open Knowledge Format

## Source details

- **Publisher:** Google Cloud Data Cloud team
- **Authors:** Sam McVeety and Amir Hormati
- **Published:** June 2026
- **Original:** [Google Cloud article](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing)
- **Official repository linked by the article:** [Open Knowledge Format](https://github.com/GoogleCloudPlatform/knowledge-catalog/tree/main/okf)
- **Source type:** Format announcement and overview

## Original summary

Google introduces **Open Knowledge Format (OKF) v0.1** as an open, portable representation for curated knowledge used by humans and agents. The article explicitly says OKF formalizes the LLM-wiki pattern into an interoperability format.

An OKF bundle is described as a directory of Markdown concept documents with YAML frontmatter. Paths identify concepts, Markdown links create a graph, and optional `index.md` and `log.md` files support navigation and history. The overview names frontmatter fields such as type, title, description, resource, tags, and timestamp, while saying that only a concept's type is required by the minimal interoperability surface.

The design emphasizes three principles:

1. **Minimal opinion:** define an interchange surface without imposing a domain content model.
2. **Producer/consumer independence:** humans, export pipelines, or LLMs may write a bundle, while different tools or agents consume it.
3. **Format rather than platform:** use files, Markdown, YAML, and version control without requiring a proprietary runtime or SDK.

The launch includes proofs of concept: a BigQuery enrichment agent, a static graph visualizer, and sample bundles. The article labels OKF v0.1 a starting point intended to evolve through open contributions.

## Evidence and limitations

This is a primary announcement and overview, not the complete specification. Conformance criteria, reserved filenames, link rules, and version behavior should be verified against the versioned repository before claiming compatibility.

The article's metadata reports June 12, 2026, while the rendered page displays June 13, 2026; this record therefore preserves only month-level dating.

Claims that OKF is vendor-neutral, portable without translation, or suitable as a universal knowledge interchange language are design goals. The reference producer, examples, and Google Cloud ingestion path are proofs of concept rather than independent cross-vendor interoperability evidence.

The source blends a genuinely minimal file format with Google Cloud product context. Adoption, extension governance, collision handling, trust, provenance, and semantic compatibility across independently authored bundles remain open questions.

The article does not grant redistribution rights for its full text, so this record contains only metadata, an original summary, and links.

## Related pages

- [[concepts/open-knowledge-format|Open Knowledge Format]]
- [[comparisons/llm-wiki-vs-okf|LLM Wiki Pattern vs OKF]]
- [[concepts/llm-wiki-pattern|LLM Wiki Pattern]]
- [[concepts/agent-harnesses|Agent harnesses]]
