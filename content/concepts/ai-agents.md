---
title: AI Agents
type: concept
tags: [agents, architecture, tools, orchestration]
sources:
  - raw/anthropic-building-effective-agents.md
  - raw/openai-practical-guide-building-agents.md
  - raw/react-synergizing-reasoning-and-acting.md
updated: 2026-07-14
publish: true
---

# AI Agents

AI agents are language-model systems that use tools and environmental feedback to pursue goals across multiple steps. The model participates in deciding what to do next rather than only producing a single response. [[raw/openai-practical-guide-building-agents|OpenAI source record]] · [[raw/anthropic-building-effective-agents|Anthropic source record]]

## Boundary and terminology

Anthropic uses **agentic systems** as an umbrella term but distinguishes fixed **workflows** from **agents**: workflows follow predefined code paths, while agents dynamically control their process and tool use. OpenAI's definition is narrower: the model must manage workflow execution, choose tools, detect completion, and recover or return control to the user. [[raw/anthropic-building-effective-agents|Anthropic source record]] · [[raw/openai-practical-guide-building-agents|OpenAI source record]]

These definitions are compatible but not identical. **Analysis:** When comparing systems, it is safer to describe who controls execution and how much of the path is predetermined than to rely on the word “agent” alone.

## Core structure

Across the practical guides, a minimal agent includes:

1. a model that interprets state and selects a next step;
2. instructions or policies that constrain behavior;
3. [[concepts/agent-tools|tools]] that retrieve information or take action;
4. observations from the environment;
5. a loop that continues until completion, failure, escalation, or another stopping condition.

OpenAI explicitly groups the foundations as model, tools, and instructions. Anthropic describes the implementation as a model using tools in a feedback loop and stresses ground truth from tool results or code execution. [[raw/openai-practical-guide-building-agents|OpenAI source record]] · [[raw/anthropic-building-effective-agents|Anthropic source record]]

[[concepts/react|ReAct]] is a research pattern that makes the reasoning–action–observation cycle explicit by interleaving task reasoning with actions and environmental observations. [[raw/react-synergizing-reasoning-and-acting|ReAct source record]]

## When agents fit

Agents are most plausible when the path cannot be specified reliably in advance: the task involves ambiguous judgment, changing context, unstructured information, or an unpredictable number of steps. Fixed automation or a single augmented model call remains preferable when it can meet the requirement more cheaply and predictably. [[raw/openai-practical-guide-building-agents|OpenAI source record]] · [[raw/anthropic-building-effective-agents|Anthropic source record]]

Useful environments also provide measurable outcomes, meaningful tool feedback, and opportunities for human review. The sources highlight coding and customer support because tests, system records, or user-defined resolutions can ground progress. [[raw/anthropic-building-effective-agents|Anthropic source record]]

## Costs and failure modes

Autonomy can improve flexibility while increasing latency, cost, and the chance that errors compound across steps. Reliability therefore depends on evaluations, clear interfaces, stopping conditions, and [[concepts/agent-safety-and-control|safety and control mechanisms]]. [[raw/anthropic-building-effective-agents|Anthropic source record]] · [[raw/openai-practical-guide-building-agents|OpenAI source record]]

## Evidence status

The architecture and deployment advice here is supported by two vendor engineering guides that report practical experience but not systematic comparative studies. ReAct contributes benchmark evidence for one reasoning-and-acting format, but its results are specific to the paper's tasks and baselines. Confidence is **medium** for broad design recommendations and should be raised only with application-specific evaluations or independent studies.

## Related

- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
- [[concepts/react|ReAct]]
