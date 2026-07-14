---
title: Agent Interoperability
type: concept
tags: [agents, interoperability, protocols, tools, orchestration]
sources:
  - raw/google-agent-tools-interoperability.md
updated: 2026-07-14
publish: true
---

# Agent Interoperability

Agent interoperability is the use of shared contracts for models, [[concepts/agent-tools|tools]], agents, interfaces, and transaction systems to discover capabilities and communicate without a bespoke integration for every pair. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 6–15)

## Protocol layers

The Google whitepaper presents several protocols at different boundaries. They are complementary rather than interchangeable. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]]

| Boundary               | Protocol discussed | Primary role                                                        |
| ---------------------- | ------------------ | ------------------------------------------------------------------- |
| Model or host ↔ tool   | MCP                | Discover and invoke data or action capabilities                     |
| Agent ↔ agent          | A2A                | Discover specialists and coordinate stateful or long-running work   |
| Agent ↔ user interface | A2UI               | Declare interactive interface intent through constrained components |
| Agent ↔ commerce       | AP2 and UCP        | Express purchasing, payment, and commerce mandates                  |

## MCP

The **Model Context Protocol (MCP)** uses host, client, and server roles to standardize tool discovery and invocation. The paper argues that this reduces repeated model-to-tool connector work and describes public, managed, and internal registries. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 10–16)

MCP standardizes an interface, not trust. Public servers may be unvetted; credentials, consent, transport security, tool descriptions, and output validation remain deployment responsibilities. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 11–16) · [[concepts/agent-safety-and-control|Agent safety and control]]

Protocol and transport claims should be versioned. A transport described by one edition of a specification should not be presented as a permanent property of the protocol. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]]

## A2A

**Agent-to-Agent (A2A)** supports discovery and coordination among specialized agents, including long-running tasks and clarification. Agent Cards advertise capabilities and endpoints. The paper contrasts this with forcing an open-ended specialist into a single request–response tool call, which can produce opaque and brittle control flow. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 17–31)

A2A therefore affects [[concepts/agent-orchestration|orchestration]] as well as transport: an implementation must define ownership of state, delegation, cancellation, retries, identity, and final synthesis.

## Constrained interfaces and transactions

A2UI is presented as a declarative alternative to running arbitrary model-generated interface code. A renderer maps agent-declared intent onto a trusted component catalog. AP2 and UCP extend explicit contracts to commerce and payments. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 32–47)

**Analysis:** Declarative protocols can reduce an attack surface but do not make generated interactions safe by default. Catalog components, action bindings, transaction mandates, and downstream services still require authorization and validation.

## Selection questions

Before adopting an interoperability protocol, evaluate:

1. which boundary it standardizes;
2. protocol and implementation maturity;
3. discovery and versioning behavior;
4. authentication, authorization, and consent;
5. state, cancellation, and failure semantics;
6. observability and audit support;
7. portability demonstrated across independent implementations.

## Evidence status

Confidence is **medium** for the architectural distinctions and **low-to-medium** for broad cost or portability benefits. The main source is a Google ecosystem whitepaper describing rapidly evolving protocols; independent interoperability testing is still needed.

## Related

- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-skills|Agent skills]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
