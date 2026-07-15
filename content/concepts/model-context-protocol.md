---
title: Model Context Protocol
type: concept
tags: [agents, tools, interoperability, protocols]
sources:
  - raw/anthropic-introducing-model-context-protocol.md
  - raw/google-agent-tools-interoperability.md
updated: 2026-07-14
publish: true
---

# Model Context Protocol

The **Model Context Protocol (MCP)** is an open protocol for connecting AI applications to external data and capabilities through shared client–server contracts. It standardizes an integration boundary; it does not itself decide which context is relevant or which action is authorized. [[raw/anthropic-introducing-model-context-protocol|Anthropic MCP announcement]] · [[raw/google-agent-tools-interoperability|Tools and interoperability source record]]

## Motivation

Anthropic's 2024 launch announcement frames MCP as an answer to repeated custom connectors between assistants and data systems. A provider exposes data or capabilities through an MCP server, while an AI application connects as a client. [[raw/anthropic-introducing-model-context-protocol|Anthropic MCP announcement]]

The later Google whitepaper places MCP at the model-or-host-to-tool boundary and contrasts it with [[concepts/agent2agent-protocol|A2A]], which coordinates autonomous peers. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 6–17)

## Architectural role

MCP can support:

- capability discovery through machine-readable definitions;
- retrieval of context from external systems;
- invocation of tools that read or change state;
- reuse of a server implementation across compatible clients.

**Analysis:** MCP is best understood as part of an [[concepts/agent-harnesses|agent harness]]. The harness still chooses servers, assembles context, scopes credentials, validates outputs, records traces, and decides whether a model may invoke a capability.

## Security boundary

A common interface can increase reuse and also increase the impact of a compromised or misleading server. Important controls include:

1. explicit server trust and provenance;
2. least-privilege credentials;
3. user consent for sensitive operations;
4. schema and output validation;
5. separation of read and write capabilities;
6. network and sandbox boundaries;
7. logging, revocation, and incident response.

The launch article calls MCP secure but does not establish that every implementation satisfies these controls. [[raw/anthropic-introducing-model-context-protocol|Anthropic MCP announcement]] · [[concepts/agent-safety-and-control|Agent safety and control]]

## Evolution and versioning

The Anthropic article is a launch snapshot, not a current specification. The Google whitepaper also describes one stage of a changing ecosystem. Implementations should pin a protocol version and verify transport, authorization, lifecycle, and compatibility behavior against that version.

See [[comparisons/mcp-vs-a2a|MCP vs A2A]] for boundary and interaction differences.

## Evidence status

Confidence is **high** that MCP originated as a shared client–server integration protocol and **medium** for broad claims that it reduces lifecycle cost or guarantees portability. Those benefits depend on conformance, semantics, trust, and independent implementations.

## Related

- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-interoperability|Agent interoperability]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
- [[comparisons/mcp-vs-a2a|MCP vs A2A]]
