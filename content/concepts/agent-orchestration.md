---
title: Agent Orchestration
type: concept
tags: [agents, orchestration, architecture, evaluation]
sources:
  - raw/anthropic-building-effective-agents.md
  - raw/openai-practical-guide-building-agents.md
  - raw/google-agent-tools-interoperability.md
  - raw/google-agent-skills.md
updated: 2026-07-14
publish: true
---

# Agent Orchestration

Agent orchestration is the control structure that coordinates model calls, [[concepts/agent-tools|tools]], workers, state, and stopping conditions while an [[concepts/ai-agents|AI agent]] or workflow pursues a goal.

## Complexity ladder

Both practical guides recommend incremental complexity. Anthropic advises starting with the simplest adequate model interaction, then using fixed workflows, and only then moving to autonomous agents when the task requires flexible planning. OpenAI similarly recommends maximizing one agent's capabilities before introducing multiple agents. [[raw/anthropic-building-effective-agents|Anthropic source record]] · [[raw/openai-practical-guide-building-agents|OpenAI source record]]

**Analysis:** This yields a useful ladder rather than a binary choice:

1. single model call, optionally with retrieval or examples;
2. deterministic multi-call workflow;
3. one tool-using agent in a bounded loop;
4. multiple coordinated agents.

A higher rung is justified only when evaluation shows that a lower rung cannot meet requirements.

## Fixed workflow patterns

Anthropic describes five reusable patterns. [[raw/anthropic-building-effective-agents|Anthropic source record]]

| Pattern             | Control structure                              | Appropriate when                                           |
| ------------------- | ---------------------------------------------- | ---------------------------------------------------------- |
| Prompt chaining     | Sequential calls with optional gates           | The task decomposes into stable ordered steps              |
| Routing             | Classify, then send to a specialist path       | Inputs fall into distinguishable categories                |
| Parallelization     | Run independent sections or multiple votes     | Work can proceed independently or needs diverse judgments  |
| Orchestrator–worker | A model creates and delegates unknown subtasks | The required subtasks depend on the input                  |
| Evaluator–optimizer | Generate, critique, and revise iteratively     | Evaluation criteria are clear and feedback improves output |

These are composable workflow patterns, not claims that every implementation needs a framework or multiple agents.

## Single-agent loop

A single agent can accumulate tools while retaining one control loop. OpenAI argues that this often keeps evaluation and maintenance simpler. Typical exits include a final response, a designated output, an error, a tool-defined termination, or a maximum number of turns. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

## Multi-agent patterns

OpenAI separates two broad multi-agent structures. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

- **Manager:** one agent retains user context and invokes specialist agents as tools, then synthesizes their results.
- **Decentralized handoffs:** peer agents transfer execution and conversation state to the specialist that should continue.

Anthropic's orchestrator–worker workflow resembles the manager pattern because a central model decomposes and synthesizes work, although the sources use different taxonomies. [[raw/anthropic-building-effective-agents|Anthropic source record]]

## Interoperable and composed execution

The tools and interoperability whitepaper distinguishes invoking a bounded tool from coordinating a specialist agent that may require clarification, long-running state, cancellation, or negotiation. It presents A2A as a protocol layer for the latter case. [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 17–31) · [[concepts/agent-interoperability|Agent interoperability]]

The Agent Skills whitepaper recommends explicit dependency structures such as directed acyclic graphs when several [[concepts/agent-skills|skills]] compose a workflow. This can make dependencies and failure propagation more inspectable than informal chains of model-selected steps. [[raw/google-agent-skills|Agent Skills source record]] (pp. 36–41)

**Tension:** OpenAI's manager pattern exposes specialist agents as tools, while the Google interoperability paper warns that treating an open-ended specialist as a simple tool creates brittle control flow. These positions can be reconciled only partly: a bounded, request–response specialist may fit a tool contract, whereas a specialist needing clarification, durable state, negotiation, or cancellation requires richer orchestration. [[raw/openai-practical-guide-building-agents|OpenAI source record]] · [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 23–31)

**Analysis:** Directed acyclic graphs favor predictable dependencies; dynamic orchestrator–worker designs favor tasks whose subtasks cannot be known in advance. Neither should be treated as a universal replacement for the other.

## Split criteria

Multiple agents become more defensible when one prompt contains excessive branching or when the system repeatedly chooses among similar tools incorrectly even after tool descriptions and parameters are improved. Agent count alone is not the decisive factor; overlap and ambiguity among responsibilities matter. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

## Evidence status

The pattern taxonomy is well specified across the practical sources, but their recommendations derive primarily from vendor-reported deployment experience. Confidence is **medium** until a proposed orchestration is compared against simpler alternatives using task-specific [[concepts/agent-evaluation|evaluations]].

## Related

- [[concepts/ai-agents|AI agents]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-interoperability|Agent interoperability]]
- [[concepts/agent-skills|Agent skills]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
- [[concepts/react|ReAct]]
