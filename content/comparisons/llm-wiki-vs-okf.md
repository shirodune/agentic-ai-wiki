---
title: LLM Wiki Pattern vs OKF
type: comparison
tags: [agents, comparison, knowledge, interoperability]
sources:
  - raw/karpathy-llm-wiki.md
  - raw/google-open-knowledge-format.md
updated: 2026-07-14
publish: true
---

# LLM Wiki Pattern vs OKF

The [[concepts/llm-wiki-pattern|LLM Wiki pattern]] and [[concepts/open-knowledge-format|Open Knowledge Format]] are related but operate at different levels. Karpathy describes a maintenance practice; Google presents OKF as a minimal exchange format inspired by that practice. [[raw/karpathy-llm-wiki|Karpathy LLM Wiki source record]] · [[raw/google-open-knowledge-format|OKF source record]]

## Comparison

| Dimension        | LLM Wiki pattern                            | Open Knowledge Format                               |
| ---------------- | ------------------------------------------- | --------------------------------------------------- |
| Primary concern  | How knowledge is accumulated and maintained | How knowledge bundles are represented and exchanged |
| Core actor       | Human curator plus LLM maintainer           | Independent producers and consumers                 |
| Main artifact    | Evolving interlinked Markdown wiki          | Versioned Markdown/YAML bundle                      |
| Structural model | Raw sources, wiki, and schema               | Concept files, metadata, links, and reserved files  |
| Operations       | Ingest, query, and lint                     | Produce, validate, exchange, and consume            |
| Governance       | Defined locally in the schema               | Minimal conformance surface plus local extensions   |
| Portability      | Possible but bespoke                        | Explicit design goal                                |
| Evidence         | Conceptual workflow note                    | v0.1 announcement and proofs of concept             |

## Complementarity

A team can maintain an LLM Wiki and export or organize parts of it as an OKF bundle. Conversely, an LLM Wiki agent could ingest an OKF bundle as a source collection.

**Analysis:** The maintenance workflow should remain distinct from the interchange contract. Conformance to a file format does not establish source quality, correct synthesis, or healthy wiki maintenance. A well-maintained local wiki may also choose richer conventions than a minimal portable format.

## Tensions

### Local richness versus interoperability

Karpathy expects each team and agent to co-evolve a schema suited to its domain. OKF minimizes required structure so independent systems can exchange files. Rich local fields can improve governance while reducing portability unless namespaced or mapped.

### Immutability versus living knowledge

The LLM Wiki keeps raw sources immutable while allowing synthesis pages to evolve. OKF concept documents can be produced or enriched by various systems. A consumer must know whether a document is evidence, interpretation, or generated synthesis; a file format alone does not settle that provenance role.

### Link and identity conventions

OKF assigns identity through file paths and describes normal Markdown links. Many practical wikis use Obsidian-style wikilinks or custom slugs. Conversion may be needed even when both sides use Markdown.

## This repository

This repository practices the LLM Wiki workflow with additional provenance, copyright, review, and publication controls. It should not claim OKF conformance until its frontmatter, links, reserved files, and validation behavior are checked against a specific OKF version.

## Evidence limits

The comparison is based on two conceptual publisher sources. There is no independent study showing that OKF improves LLM Wiki quality or that an LLM Wiki outperforms other knowledge architectures. Both should be evaluated through real producer, consumer, and maintenance workflows.

## Related

- [[concepts/llm-wiki-pattern|LLM Wiki Pattern]]
- [[concepts/open-knowledge-format|Open Knowledge Format]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-interoperability|Agent interoperability]]
