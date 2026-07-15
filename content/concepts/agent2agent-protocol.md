---
title: Agent2Agent Protocol
type: concept
tags: [agents, interoperability, orchestration, protocols]
sources:
  - raw/google-announcing-agent2agent-protocol.md
  - raw/google-agent-tools-interoperability.md
updated: 2026-07-14
publish: true
---

# Agent2Agent Protocol

The **Agent2Agent Protocol (A2A)** is an open protocol intended to let autonomous agents discover one another, exchange messages, and coordinate tasks across framework or vendor boundaries. The 2025 launch announcement positions it as complementary to [[concepts/model-context-protocol|MCP]], not a replacement. [[raw/google-announcing-agent2agent-protocol|Google A2A announcement]]

## Launch design

The launch article names five principles:

1. preserve open-ended agent capabilities rather than forcing every interaction into a tool call;
2. build on existing web standards;
3. support enterprise authentication and authorization;
4. accommodate long-running tasks and human involvement;
5. carry multiple modalities.

These are intended design properties, not evidence that every implementation achieves them. [[raw/google-announcing-agent2agent-protocol|Google A2A announcement]]

## Interaction model

The draft-era model distinguishes a **client agent**, which formulates a task, from a **remote agent**, which acts on it. The announcement introduces:

- **Agent Cards** for capability discovery;
- tasks with lifecycle and status;
- artifacts as task outputs;
- messages for context, instructions, and results;
- content parts for modality or interface negotiation.

The later interoperability whitepaper adds detail about discovery, extensions, stateful work, and coordination. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 17–31)

## Orchestration implications

A2A does not remove [[concepts/agent-orchestration|orchestration]] decisions. A deployment must still determine:

- who owns user context and task state;
- whether delegation is allowed;
- how identity and authority propagate;
- timeout, cancellation, retry, and compensation behavior;
- which agent synthesizes or approves the result;
- how messages and artifacts are audited.

**Analysis:** A2A is most defensible when the remote capability is genuinely agentic—stateful, clarifying, long-running, or independently governed. A bounded deterministic operation may remain simpler as a normal [[concepts/agent-tools|tool]].

## Security and trust

Agent discovery is not agent trust. Cards, endpoints, messages, artifacts, and delegated authority require authentication, authorization, validation, policy enforcement, and provenance. “Secure by default” in the launch article should be read as an aspiration, not a verified property. [[concepts/agent-safety-and-control|Agent safety and control]]

## Evolution and versioning

The April 2025 article explicitly describes a draft and future production-ready release. Current implementations should use a versioned specification rather than infer behavior from the launch announcement.

See [[comparisons/mcp-vs-a2a|MCP vs A2A]] for a direct comparison.

## Evidence status

Confidence is **high** for the protocol's launch intent and **medium** for the architectural distinction between tool access and agent collaboration. Claims of universal cross-vendor interoperability, lower cost, or seamless collaboration remain unverified without conformance and deployment evidence.

## Related

- [[concepts/agent-interoperability|Agent interoperability]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/model-context-protocol|Model Context Protocol]]
- [[concepts/agent-tools|Agent tools]]
- [[comparisons/mcp-vs-a2a|MCP vs A2A]]
