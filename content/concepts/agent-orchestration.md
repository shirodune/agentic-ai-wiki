---
title: Agent Orchestration
type: concept
tags: [agents, orchestration, architecture, evaluation]
sources:
  - raw/anthropic-building-effective-agents.md
  - raw/openai-practical-guide-building-agents.md
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

## Split criteria

Multiple agents become more defensible when one prompt contains excessive branching or when the system repeatedly chooses among similar tools incorrectly even after tool descriptions and parameters are improved. Agent count alone is not the decisive factor; overlap and ambiguity among responsibilities matter. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

## Evidence status

The pattern taxonomy is well specified by the two source organizations, but their recommendations derive from vendor-reported deployment experience. Confidence is **medium** until a proposed orchestration is compared against simpler alternatives using task-specific evaluations.

## Related

- [[concepts/ai-agents|AI agents]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
- [[concepts/react|ReAct]]
