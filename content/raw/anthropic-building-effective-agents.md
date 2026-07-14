---
title: Building Effective Agents
type: source
tags: [agents, orchestration, tools, evaluation, safety]
sources: []
updated: 2026-07-14
publish: true
source_url: https://www.anthropic.com/engineering/building-effective-agents
accessed: 2026-07-14
redistribution: link-summary-only
---

# Building Effective Agents

## Source metadata

- **Publisher:** Anthropic
- **Authors:** Erik S. and Barry Zhang
- **Displayed publication date:** 2024-12-19
- **Format:** Engineering article
- **Original:** [Anthropic Engineering](https://www.anthropic.com/engineering/building-effective-agents)

## Original summary

Anthropic distinguishes **workflows**, where predefined code paths orchestrate language models and tools, from **agents**, where the model dynamically controls its process and tool use. It recommends beginning with the simplest adequate design and accepting agentic complexity only when gains justify additional latency, cost, and error risk.

The article presents an augmented language model—equipped with retrieval, tools, and memory—as the basic building block. It then describes prompt chaining, routing, parallelization, orchestrator–worker, and evaluator–optimizer workflows before discussing autonomous tool-use loops.

For autonomous agents, the article emphasizes environmental feedback, explicit stopping conditions, human checkpoints, sandboxed testing, transparent plans, and carefully designed tool interfaces. It argues that tool definitions deserve substantial engineering attention because ambiguous or awkward interfaces can become a major source of failure.

## Important claims

- Fixed workflows are preferable when a task is predictable; dynamic agents are better suited to open-ended tasks whose required steps cannot be hard-coded.
- Prompt chaining, routing, parallelization, orchestrator–worker, and evaluator–optimizer are reusable orchestration patterns rather than mandatory architectures.
- Effective agents repeatedly act, inspect environmental results, and adjust until completion or a stopping condition.
- Tool documentation, parameter design, examples, and error-resistant interfaces are central to agent reliability.
- Coding and customer support are presented as promising domains because actions can be grounded in tools, outcomes can be evaluated, and humans can remain in the loop.

## Limitations and provenance notes

This is a vendor-authored engineering guide based largely on Anthropic's stated customer and internal experience, not a systematic empirical comparison. Product examples may reflect Anthropic's ecosystem.

**Analysis:** Although the page displays a 2024-12-19 publication date, the version accessed on 2026-07-14 referenced later Claude 4.5 models. The page may therefore have received post-publication edits without a changed headline date; the access date is important when citing it.

The copyright status does not clearly permit republication of the article body, so this record preserves only metadata, an original summary, and links.

## Related pages

- [[concepts/ai-agents|AI agents]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
