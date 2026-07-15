---
title: LLM Wiki Pattern
type: concept
tags: [agents, knowledge, memory, research]
sources:
  - raw/karpathy-llm-wiki.md
  - raw/google-open-knowledge-format.md
updated: 2026-07-14
publish: true
---

# LLM Wiki Pattern

The **LLM Wiki pattern** uses an LLM agent to incrementally compile curated sources into a persistent, interlinked Markdown knowledge base. Its key claim is organizational: synthesis, cross-references, and contradictions should accumulate in a maintained artifact rather than be reconstructed from raw documents for every question. [[raw/karpathy-llm-wiki|Karpathy LLM Wiki source record]]

## Three layers

Karpathy separates the system into:

1. **Raw sources:** curated and immutable evidence.
2. **The wiki:** agent-maintained summaries, concepts, entities, comparisons, and filed answers.
3. **The schema:** conventions and procedures that govern the agent's maintenance work.

This separation assigns source curation and direction to the human while the agent performs filing, synthesis, and bookkeeping. [[raw/karpathy-llm-wiki|Karpathy LLM Wiki source record]]

## Operating loop

The pattern compounds through three operations:

- **Ingest:** integrate a new source across all qualifying pages.
- **Query:** answer from the compiled wiki and retain valuable synthesis.
- **Lint:** detect broken links, orphan pages, stale claims, contradictions, and research gaps.

`index.md` provides content-oriented navigation, while `log.md` preserves chronological maintenance history.

## Relationship to retrieval

The source contrasts a maintained wiki with query-time retrieval that repeatedly reconstructs knowledge from raw chunks.

**Analysis:** This is not an exclusive choice. A growing wiki may still use lexical or semantic retrieval to locate its compiled pages. The stronger distinction is between retrieving **maintained synthesis** and repeatedly synthesizing only from raw material.

## Governance requirements

A reliable implementation needs more than Markdown generation:

- explicit source approval and provenance;
- separation of evidence from inference;
- contradiction and uncertainty tracking;
- copyright-aware handling of source bodies;
- review before public release;
- version history and rollback;
- link, schema, and publication validation.

These controls are local extensions to the abstract pattern. This repository implements such extensions through its schema and publication policy.

## Relationship to OKF

[[concepts/open-knowledge-format|Open Knowledge Format]] formalizes a minimal interchange surface for file-based knowledge. The LLM Wiki pattern describes how knowledge is maintained; OKF describes how a bundle may be represented for exchange. [[raw/google-open-knowledge-format|OKF source record]]

See [[comparisons/llm-wiki-vs-okf|LLM Wiki Pattern vs OKF]].

## Evidence status

Confidence is **high** that the pattern accurately describes a practical agent-maintained wiki workflow. Confidence is **low-to-medium** for claims that it outperforms retrieval generally or makes maintenance nearly free; those outcomes depend on scale, model quality, review effort, and error control.

## Related

- [[concepts/open-knowledge-format|Open Knowledge Format]]
- [[comparisons/llm-wiki-vs-okf|LLM Wiki Pattern vs OKF]]
- [[concepts/agent-skills|Agent skills]]
- [[concepts/agent-harnesses|Agent harnesses]]
