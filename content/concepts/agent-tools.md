---
title: Agent Tools
type: concept
tags: [agents, tools, architecture, safety]
sources:
  - raw/anthropic-building-effective-agents.md
  - raw/openai-practical-guide-building-agents.md
  - raw/react-synergizing-reasoning-and-acting.md
  - raw/google-agent-tools-interoperability.md
  - raw/google-agent-skills.md
updated: 2026-07-14
publish: true
---

# Agent Tools

Agent tools are external functions, APIs, retrieval systems, user-interface controls, or specialist agents through which an [[concepts/ai-agents|AI agent]] obtains information or changes its environment.

## Roles

OpenAI groups tools into three functional types. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

- **Data tools** retrieve context, such as records, documents, or search results.
- **Action tools** change external state, such as sending a message or updating a record.
- **Orchestration tools** expose specialist agents as callable capabilities.

Anthropic places retrieval, tools, and memory around an augmented language model and emphasizes that the model must receive environmental results as ground truth during execution. [[raw/anthropic-building-effective-agents|Anthropic source record]]

In [[concepts/react|ReAct]], actions alternate with observations so that new evidence can update the next reasoning step. [[raw/react-synergizing-reasoning-and-acting|ReAct source record]]

## Tools, protocols, and skills

A tool exposes a capability; an interoperability protocol standardizes how that capability is discovered or invoked; an [[concepts/agent-skills|agent skill]] packages procedural guidance for deciding how to perform recurring work. These layers can be combined but should not be conflated. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 6–17) · [[raw/google-agent-skills|Agent Skills source record]] (pp. 11–14)

[[concepts/agent-interoperability|MCP]] can reduce bespoke model-to-tool connector code, while A2A addresses stateful coordination among agents. Neither protocol removes the need for clear semantics, scoped credentials, validation, and observability. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 10–31)

## Interface quality

Both practical guides argue that tool quality affects behavior, not merely developer convenience. Standardized definitions, descriptive names, clear parameters, examples, edge-case behavior, and explicit boundaries improve selection and reduce avoidable errors. [[raw/openai-practical-guide-building-agents|OpenAI source record]] · [[raw/anthropic-building-effective-agents|Anthropic source record]]

Anthropic calls this design problem the **agent–computer interface (ACI)** and compares its importance to human–computer interface design. It recommends choosing formats that are natural for the model and avoiding unnecessary formatting burdens. [[raw/anthropic-building-effective-agents|Anthropic source record]]

OpenAI notes that overlapping tools can cause selection failures even when there are relatively few tools. It recommends improving tool clarity before splitting a system into more agents. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

## Risk-aware design

Tool permissions should match the minimum capability needed for the task. OpenAI recommends rating tools by properties such as read versus write access, reversibility, required permissions, and financial impact, then using those ratings to trigger additional checks or human approval. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

See [[concepts/agent-safety-and-control|Agent safety and control]] for layered guardrails and escalation.

## Analysis: tool contract checklist

The sources jointly imply that a production tool contract should specify:

1. purpose and non-goals;
2. parameter meanings and valid ranges;
3. required permissions;
4. success and failure outputs;
5. side effects and reversibility;
6. examples and edge cases;
7. risk class and approval requirements;
8. how observations are returned to the agent.

This checklist is synthesis, not a verbatim framework from either source.

## Evidence status

The interface recommendations are consistent across several vendor guides and conceptually supported by ReAct's use of observations. Confidence is **medium** because reliability still depends on model, task, protocol implementation, and [[concepts/agent-evaluation|deployment-specific testing]].

## Related

- [[concepts/ai-agents|AI agents]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-interoperability|Agent interoperability]]
- [[concepts/agent-skills|Agent skills]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
- [[concepts/react|ReAct]]
