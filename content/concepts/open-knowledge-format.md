---
title: Open Knowledge Format
type: concept
tags: [agents, knowledge, interoperability, protocols]
sources:
  - raw/google-open-knowledge-format.md
  - raw/karpathy-llm-wiki.md
updated: 2026-07-14
publish: true
---

# Open Knowledge Format

**Open Knowledge Format (OKF)** is an open, file-based format for exchanging curated knowledge between humans, tools, and agents. Google describes OKF v0.1 as a formalization of the [[concepts/llm-wiki-pattern|LLM Wiki pattern]] using Markdown documents, YAML frontmatter, paths, and links. [[raw/google-open-knowledge-format|OKF source record]] · [[raw/karpathy-llm-wiki|Karpathy LLM Wiki source record]]

## Bundle model

The launch overview describes an OKF bundle as a directory in which:

- one Markdown file represents one concept;
- the file path identifies that concept;
- YAML frontmatter carries structured metadata;
- Markdown links form a graph;
- `index.md` and `log.md` may support navigation and history.

The overview says a concept's `type` is the only required field in the minimal interoperability surface, while naming title, description, resource, tags, and timestamp as useful structured fields.

## Design principles

OKF is presented around three principles:

1. **Minimal opinion:** standardize exchange without imposing a domain ontology.
2. **Producer/consumer independence:** allow different humans, pipelines, or agents to write and read bundles.
3. **Format, not platform:** avoid requiring a proprietary account, runtime, or SDK.

These principles are goals. Independent implementations and conformance evidence are needed to establish practical interoperability. [[raw/google-open-knowledge-format|OKF source record]]

## Relationship to agent context

OKF standardizes a representation of maintained knowledge, not how an agent selects, retrieves, trusts, or applies it. An [[concepts/agent-harnesses|agent harness]] still needs search, context assembly, access control, provenance checks, and evaluation.

**Analysis:** A portable knowledge bundle can reduce integration friction while also carrying stale, malicious, or incompatible content. Producers and consumers need trust, version, and namespace policies.

## Versioning and conformance

The announcement labels v0.1 a starting point. Claims about required fields, reserved files, link behavior, or backward compatibility should be tied to a specific specification version.

This Agentic AI Wiki is influenced by the same file-based pattern but is **not claimed to be OKF-conformant**. Its Obsidian-style wikilinks, frontmatter, source-record model, and publication fields require comparison with the versioned conformance rules before making that claim.

See [[comparisons/llm-wiki-vs-okf|LLM Wiki Pattern vs OKF]].

## Evidence status

Confidence is **high** for the v0.1 design intent described by its publisher and **low-to-medium** for universal portability or vendor neutrality in practice. The launch evidence consists of Google proofs of concept and sample bundles, not broad independent adoption.

## Related

- [[concepts/llm-wiki-pattern|LLM Wiki Pattern]]
- [[comparisons/llm-wiki-vs-okf|LLM Wiki Pattern vs OKF]]
- [[concepts/agent-interoperability|Agent interoperability]]
- [[concepts/agent-harnesses|Agent harnesses]]
