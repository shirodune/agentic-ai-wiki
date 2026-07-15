---
title: Introducing the Model Context Protocol
type: source
tags: [agents, tools, interoperability, protocols]
sources: []
updated: 2026-07-14
publish: true
source_url: https://www.anthropic.com/news/model-context-protocol
accessed: 2026-07-14
redistribution: link-summary-only
---

# Introducing the Model Context Protocol

## Source details

- **Publisher:** Anthropic
- **Published:** November 25, 2024
- **Original:** [Anthropic announcement](https://www.anthropic.com/news/model-context-protocol)
- **Linked project:** [Model Context Protocol](https://modelcontextprotocol.io/)
- **Source type:** Protocol launch announcement

## Original summary

Anthropic introduces the **Model Context Protocol (MCP)** as an open standard for connecting AI applications to data sources and tools. The announcement frames the motivating problem as repeated bespoke integrations: each assistant and data source otherwise needs a custom connector.

The launch architecture distinguishes **MCP servers**, which expose data or capabilities, from AI applications acting as **MCP clients**. Anthropic announced a specification and SDKs, local server support in Claude Desktop, and an open-source server repository. Initial examples included connectors for services such as Google Drive, Slack, GitHub, Git, Postgres, and Puppeteer.

The source presents MCP as a two-way connection rather than merely a retrieval interface. Its broader ambition is for assistants to retain useful context while moving among tools and datasets through a common protocol.

Anthropic attributes MCP's creation to David Soria Parra and Justin Spahr-Summers and describes it as a collaborative open-source ecosystem.

## Evidence and limitations

This is a primary source for MCP's launch, original motivation, and initial architecture. It is not the current protocol specification, and implementation or transport details may have changed since November 2024.

Claims that a shared protocol is simpler, more reliable, or more sustainable than bespoke connectors are architectural propositions and ecosystem forecasts, not comparative deployment evidence in this announcement. “Secure” describes a design aim; the article does not provide a complete threat model or prove that every MCP implementation is secure.

The announcement is also product-linked: it highlights Claude Desktop, Claude for Work, Claude 3.5 Sonnet, and Anthropic-maintained examples. Early-adopter statements and projected ecosystem benefits should therefore remain attributed.

The page does not state redistribution terms for the article, so this record contains only metadata, an original summary, and links.

## Related pages

- [[concepts/model-context-protocol|Model Context Protocol]]
- [[comparisons/mcp-vs-a2a|MCP vs A2A]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-interoperability|Agent interoperability]]
