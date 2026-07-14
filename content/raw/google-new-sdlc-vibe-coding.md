---
title: The New SDLC With Vibe Coding
type: source
tags: [agents, development, architecture, orchestration, evaluation]
sources: []
updated: 2026-07-14
publish: true
source_url: https://www.kaggle.com/whitepaper-the-new-SDLC-with-vibe-coding
accessed: 2026-07-14
redistribution: link-summary-only
---

# The New SDLC With Vibe Coding

## Source metadata

- **Authors:** Addy Osmani, Shubham Saboo, and Sokratis Kartakis
- **Publisher:** Google via Kaggle
- **Date:** May 2026
- **Length:** 51 pages
- **Kaggle page:** [The New SDLC With Vibe Coding](https://www.kaggle.com/whitepaper-the-new-SDLC-with-vibe-coding)
- **Official PDF:** [Google Drive](https://drive.google.com/file/d/1IR7CddF_2FyQo_PdfBNTaEA50EGiVt2r/view)

## Original summary

The paper describes a spectrum from casual **vibe coding**, where developers accept AI-generated implementations with minimal scrutiny, to **agentic engineering**, where models operate inside deliberately designed specifications, tests, permissions, feedback loops, and human oversight. It argues that the important distinction is not whether AI generates code but whether the surrounding development system makes its output dependable (pp. 10–15).

It reframes software development as a “factory” in which the developer's main artifact is the system that produces and verifies software. The model is only one component of a broader **harness** containing context, tools, memory, orchestration, constraints, evaluators, sandboxes, and observability. The paper maps this model across requirements, implementation, testing, review, deployment, and maintenance (pp. 19–30).

The developer's role is described as moving from direct implementation toward two complementary modes: a hands-on **conductor** guiding one agent and an asynchronous **orchestrator** delegating work across agents. The paper warns of an “80% problem”: generating an initial implementation can be fast while integration, edge cases, verification, and production hardening remain costly (pp. 31–35).

Its economic argument contrasts low-upfront-cost vibe coding with higher downstream maintenance, security, and review costs, versus agentic engineering's higher investment in harnesses and evaluations but lower expected operational burden (pp. 39–42).

## Important claims

- Agent reliability depends on the context and control system surrounding the model, not on model capability alone.
- Specifications, tests, evaluations, and feedback loops distinguish disciplined agentic engineering from ad hoc generation.
- Faster code generation can shift rather than remove bottlenecks, especially toward review, integration, and maintenance.
- Context engineering includes selecting, structuring, and refreshing the information available to an agent.
- Organizations should adopt agentic development incrementally and measure outcomes rather than equating generated-code volume with productivity.

## Limitations and provenance notes

This is an industry whitepaper from Google course authors, not a peer-reviewed controlled study. It combines conceptual frameworks, selected external statistics, product examples, and practitioner recommendations. Broad adoption and productivity figures depend on cited third-party sources and should be independently checked before reuse as standalone facts.

Terms such as “factory model,” “80% problem,” and the economic comparison are explanatory frameworks rather than established universal laws. The claims may reflect Google tooling and the rapidly changing 2026 coding-agent market.

The document contains editorial provenance problems: it introduces five agent components and then refers to “these four parts” (p. 11), and some endnote numbering appears misaligned with body claims. Benchmark anecdotes about harness improvements and claims about migration-free production deployment do not provide enough methodology to support general conclusions.

The copyright status does not clearly permit republication of the PDF, so this record contains only metadata, an original summary, and links.

## Related pages

- [[concepts/agentic-engineering|Agentic engineering]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/spec-driven-development|Spec-driven development]]
- [[concepts/agent-evaluation|Agent evaluation]]
- [[concepts/ai-agents|AI agents]]
