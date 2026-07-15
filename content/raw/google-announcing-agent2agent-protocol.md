---
title: Announcing the Agent2Agent Protocol
type: source
tags: [agents, interoperability, orchestration, protocols]
sources: []
updated: 2026-07-14
publish: true
source_url: https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/
accessed: 2026-07-14
redistribution: link-summary-only
---

# Announcing the Agent2Agent Protocol

## Source details

- **Publisher:** Google Developers Blog
- **Authors:** Rao Surapaneni, Miku Jha, Michael Vakoc, and Todd Segal
- **Published:** April 9, 2025
- **Original:** [Google announcement](https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/)
- **Source type:** Draft-protocol launch announcement

## Original summary

Google introduces **Agent2Agent (A2A)** as an open protocol for communication and coordination among agents built with different frameworks or by different vendors. The announcement explicitly positions A2A as complementary to Anthropic's MCP: MCP supplies an agent with tools and context, while A2A addresses collaboration between agents.

Five launch principles are presented: preserve agentic rather than tool-only interaction, build on existing web standards, support enterprise authentication and authorization, accommodate long-running tasks, and carry multiple modalities.

The described interaction has a client agent formulate a task and a remote agent act on it. Important protocol concepts include:

- an **Agent Card** for capability discovery;
- a task object with a lifecycle and status updates;
- artifacts as task outputs;
- messages carrying context, instructions, and artifacts;
- content parts that support format or interface negotiation.

The article illustrates these ideas with a candidate-sourcing workflow involving several specialist agents. It also lists more than 50 launch partners and includes extensive partner endorsements.

## Evidence and limitations

This is a primary historical source for A2A's launch rationale, draft-era concepts, and intended relationship to MCP. The article says the specification was a draft and that a production-ready version was planned later, so it must not be treated as the current specification.

Statements about seamless cross-vendor collaboration, lower costs, greater autonomy, or secure interoperability are design goals and forecasts. The announcement supplies no conformance results, independent interoperability tests, security evaluation, or comparative cost study.

The article is Google-authored and heavily promotional. Partner quotations demonstrate launch support but do not establish protocol performance or adoption. Claims about specific transports, authentication, task fields, or discovery behavior should be checked against a versioned specification before implementation.

The page does not state redistribution terms for the article, so this record contains only metadata, an original summary, and links.

## Related pages

- [[concepts/agent2agent-protocol|Agent2Agent Protocol]]
- [[comparisons/mcp-vs-a2a|MCP vs A2A]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-interoperability|Agent interoperability]]
