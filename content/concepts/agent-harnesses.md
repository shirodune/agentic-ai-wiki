---
title: Agent Harnesses
type: concept
tags: [agents, architecture, orchestration, safety, evaluation]
sources:
  - raw/anthropic-building-effective-agents.md
  - raw/openai-practical-guide-building-agents.md
  - raw/google-new-sdlc-vibe-coding.md
  - raw/google-vibe-coding-agent-security-evaluation.md
  - raw/google-spec-driven-production-development.md
  - raw/karpathy-llm-wiki.md
  - raw/google-open-knowledge-format.md
updated: 2026-07-14
publish: true
---

# Agent Harnesses

An agent harness is the software and policy environment surrounding a model that gives an [[concepts/ai-agents|AI agent]] context, state, [[concepts/agent-tools|tools]], a control loop, constraints, evaluation, and operational visibility. The model proposes behavior; the harness mediates what information and authority turn those proposals into action. [[raw/google-new-sdlc-vibe-coding|New SDLC source record]] (pp. 24–30) · [[raw/google-vibe-coding-agent-security-evaluation|Security and evaluation source record]] (pp. 8–12)

## Components

Across the sources, a production harness may include:

- context assembly and retrieval;
- instructions, policies, and [[concepts/spec-driven-development|specifications]];
- memory and session state;
- tool dispatch and [[concepts/agent-interoperability|interoperability]] clients;
- [[concepts/agent-orchestration|orchestration]], retries, and stopping conditions;
- sandboxes, permissions, network boundaries, and approval gates;
- deterministic checks and [[concepts/agent-evaluation|evaluators]];
- traces, metrics, audit records, and deployment infrastructure.

Anthropic's “augmented LLM” and tool-use loop cover the functional core, while OpenAI groups the foundations as model, tools, and instructions. The Google papers extend the surrounding system into production, security, and SDLC controls. [[raw/anthropic-building-effective-agents|Anthropic source record]] · [[raw/openai-practical-guide-building-agents|OpenAI source record]] · [[raw/google-new-sdlc-vibe-coding|New SDLC source record]] (pp. 10–30)

## External enforcement

A central safety principle is that critical restrictions should not depend on the model remembering or obeying a prompt. Sandboxing, scoped credentials, policy checks, network controls, and approval gates should be enforced externally by the harness. [[raw/google-vibe-coding-agent-security-evaluation|Security and evaluation source record]] (pp. 9–26) · [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 26–35)

This extends [[concepts/agent-safety-and-control|agent safety and control]] from output filtering to the complete execution environment.

## Harness versus framework

A framework is an implementation library; a harness is an architectural role. A harness can be built directly or through one or more frameworks. Anthropic cautions that framework abstractions can obscure prompts, responses, and control flow, so teams should retain visibility into the actual harness behavior. [[raw/anthropic-building-effective-agents|Anthropic source record]]

## Knowledge substrate

An agent harness may consume a maintained [[concepts/llm-wiki-pattern|LLM Wiki]] or a portable [[concepts/open-knowledge-format|OKF]] bundle as context. The knowledge representation does not decide retrieval, trust, permissions, or context priority; those remain harness responsibilities. [[raw/karpathy-llm-wiki|Karpathy LLM Wiki source record]] · [[raw/google-open-knowledge-format|OKF source record]]

## Verification boundary

**Analysis:** The harness should be evaluated as part of the agent, not treated as neutral plumbing. Tool schemas, context selection, retry logic, permissions, and termination behavior can change outcomes even with the same model.

Useful harness tests include:

1. context and instruction selection;
2. tool routing and parameter validation;
3. permission and sandbox enforcement;
4. recovery from tool errors and partial state;
5. stopping and escalation behavior;
6. trace completeness and privacy;
7. outcome quality under realistic load and multi-step tasks.

## Evidence status

Confidence is **medium**. Multiple practical sources agree on the importance of surrounding controls, but “harness” boundaries vary among systems and the complete architectures proposed by the Google papers lack independent comparative validation.

## Related

- [[concepts/ai-agents|AI agents]]
- [[concepts/agentic-engineering|Agentic engineering]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
- [[concepts/agent-evaluation|Agent evaluation]]
