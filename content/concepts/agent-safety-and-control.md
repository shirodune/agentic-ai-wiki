---
title: Agent Safety and Control
type: concept
tags: [agents, safety, guardrails, evaluation, tools]
sources:
  - raw/anthropic-building-effective-agents.md
  - raw/openai-practical-guide-building-agents.md
  - raw/react-synergizing-reasoning-and-acting.md
  - raw/google-vibe-coding-agent-security-evaluation.md
  - raw/google-spec-driven-production-development.md
updated: 2026-07-14
publish: true
---

# Agent Safety and Control

Agent safety and control covers the mechanisms that bound an [[concepts/ai-agents|AI agent]], detect unsafe or ineffective behavior, and transfer authority when autonomous execution should not continue.

## Layered controls

OpenAI describes guardrails as a layered defense rather than a complete security solution. It recommends combining model-based and deterministic checks with authentication, authorization, access control, and ordinary software-security practices. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

Its examples include relevance and safety classifiers, personally identifiable information filters, moderation, deterministic input checks, output validation, and safeguards linked to [[concepts/agent-tools|tool]] risk. The guide recommends adding controls in response to observed edge cases while balancing security and user experience. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

The Google security whitepaper expands this into an author-proposed seven-pillar architecture spanning infrastructure, data, model behavior, application runtime, identity and access, observability and response, and governance. It recommends enforcing critical restrictions outside the model through the [[concepts/agent-harnesses|agent harness]]. [[raw/google-vibe-coding-agent-security-evaluation|Security and evaluation source record]] (pp. 9–26)

## Continuous authorization

Static credentials answer whether an identity may access a service, not whether a particular autonomous action matches the user's current intent. The source therefore recommends contextual authorization, short-lived downscoped credentials, unique agent identities, and checkpoints for high-impact actions. [[raw/google-vibe-coding-agent-security-evaluation|Security and evaluation source record]] (pp. 18–26)

**Analysis:** A useful reconciliation of the source's identity terminology is to give the agent a dedicated workload identity while deriving narrowly scoped authority from the authenticated user and current task. For severe anomalies, controls should immediately deny side effects and egress, then snapshot or quarantine state for diagnosis rather than allowing continued execution.

[[concepts/agent-interoperability|Interoperability]] broadens this boundary: registries, remote tools, and peer agents introduce supply-chain, spoofing, delegation, and lateral-movement risks that must be governed separately from model output safety.

## Runtime control

Anthropic emphasizes repeated grounding in environmental results, human checkpoints, explicit stopping conditions, sandboxed testing, and transparent plans. It warns that autonomy can increase cost and allow errors to compound across a long trajectory. [[raw/anthropic-building-effective-agents|Anthropic source record]]

OpenAI adds two general escalation triggers: exceeding retry or failure thresholds, and attempting sensitive, irreversible, or high-impact actions. [[raw/openai-practical-guide-building-agents|OpenAI source record]]

The spec-driven development paper applies the same principles to coding agents through deterministic guardrails, restricted execution, policy services, context hygiene, and human checkpoints for sensitive operations. [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 26–35)

## Observability and evaluation

A control system needs enough trace data to determine what the model saw, which action it selected, what the tool returned, and why execution stopped. [[concepts/react|ReAct]] demonstrates an explicit reasoning–action–observation trajectory and reports improved inspectability relative to baselines without both reasoning and action components. [[raw/react-synergizing-reasoning-and-acting|ReAct source record]]

**Analysis:** Inspectability supports debugging but does not prove safety or correctness. A readable trajectory may still contain an invalid assumption, a misleading explanation, or an unsafe action. Outcome-based checks and permission boundaries remain necessary.

Security asks whether the agent remained inside authorized boundaries; [[concepts/agent-evaluation|agent evaluation]] asks whether the bounded behavior achieved the intended outcome at acceptable quality and cost. A system can pass one and fail the other. [[raw/google-vibe-coding-agent-security-evaluation|Security and evaluation source record]] (pp. 27–39)

## Analysis: control points by stage

| Stage          | Representative controls                                                |
| -------------- | ---------------------------------------------------------------------- |
| Input          | Scope, injection, privacy, and moderation checks                       |
| Planning       | Policy-constrained instructions and bounded task scope                 |
| Tool selection | Least privilege, risk classes, and approval gates                      |
| Execution      | Sandboxing, time or turn limits, and reversible operations             |
| Observation    | Structured errors, environmental ground truth, and trace capture       |
| Output         | Validation, policy checks, and evidence requirements                   |
| Escalation     | Human handoff after uncertainty, repeated failure, or high-risk action |

This table synthesizes the source recommendations; it is not a source-authored standard.

## Open questions

- Which guardrail layers reduce real failures rather than merely shifting them?
- How should false positives and false negatives be measured for each control?
- Which actions require prior approval, and which can be safely reversed afterward?
- What trace information can be retained without exposing private data or sensitive prompts?

## Evidence status

The operational recommendations agree across several practical guides, but the complete control stacks are not supported by comprehensive comparative evaluations. Confidence is **medium**; controls should be threat-modeled and tested in the actual deployment environment. The Google seven-pillar model should be treated as a proposed organizing framework, not a validated standard.

## Related

- [[concepts/ai-agents|AI agents]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-interoperability|Agent interoperability]]
- [[concepts/agent-evaluation|Agent evaluation]]
- [[concepts/react|ReAct]]
