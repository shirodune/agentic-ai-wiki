---
title: Agentic Engineering
type: concept
tags: [agents, development, architecture, evaluation, safety]
sources:
  - raw/anthropic-building-effective-agents.md
  - raw/google-new-sdlc-vibe-coding.md
  - raw/google-vibe-coding-agent-security-evaluation.md
  - raw/google-spec-driven-production-development.md
updated: 2026-07-14
publish: true
---

# Agentic Engineering

Agentic engineering is a software-development discipline in which [[concepts/ai-agents|AI agents]] generate or modify software inside human-designed specifications, tests, permissions, feedback loops, and review processes. It contrasts with casual **vibe coding**, where natural-language intent is accepted as implementation with limited verification. [[raw/google-new-sdlc-vibe-coding|New SDLC source record]] (pp. 10–15) · [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 5–7)

## Spectrum rather than binary

The Google whitepapers place development approaches on a spectrum. The differentiator is not whether AI writes code but how much control surrounds its work. [[raw/google-new-sdlc-vibe-coding|New SDLC source record]] (pp. 12–15)

| Dimension    | Casual vibe coding                     | Agentic engineering                            |
| ------------ | -------------------------------------- | ---------------------------------------------- |
| Intent       | Broad conversational request           | Reviewed specification and acceptance criteria |
| Execution    | Ad hoc generation and repair           | Bounded harness with tools and state           |
| Verification | Visual inspection or immediate success | Automated tests, evaluations, and review       |
| Permissions  | Often inherited ambient access         | Least privilege, sandboxes, and approval gates |
| Human role   | Prompt and accept                      | Architect, constrain, inspect, and decide      |
| Lifecycle    | Prototype-oriented                     | Versioned, observable, and production-governed |

This table is wiki synthesis, not a standardized maturity model.

## Factory model

The “factory” framing treats the developer's primary artifact as the system that produces and verifies software rather than only the generated code. That system includes context, specifications, tool interfaces, tests, sandboxes, review gates, deployment controls, and telemetry. [[raw/google-new-sdlc-vibe-coding|New SDLC source record]] (pp. 19–30)

The practical implication is that model selection is only one design decision. Reliability also depends on how the agent receives context, which actions it may take, what evidence determines success, and who can authorize release. See [[concepts/agent-tools|Agent tools]], [[concepts/agent-safety-and-control|Agent safety and control]], and [[concepts/agent-evaluation|Agent evaluation]].

## Changing bottlenecks

The sources argue that rapid implementation can move bottlenecks downstream to requirements, review, integration, testing, and maintenance. They warn that an impressive first draft may conceal expensive remaining work—the “80% problem” or “illusion of speed.” [[raw/google-new-sdlc-vibe-coding|New SDLC source record]] (pp. 31–41) · [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 5–7)

**Analysis:** Generated-code volume is therefore a weak productivity measure. More defensible measures include accepted lead time, escaped defects, review burden, rework, recovery cost, and sustained task success.

## Human roles

The New SDLC paper distinguishes a **conductor**, who directs an agent interactively, from an **orchestrator**, who delegates bounded work asynchronously across agents. Both remain responsible for architecture and judgment. [[raw/google-new-sdlc-vibe-coding|New SDLC source record]] (pp. 31–35)

Production guidance adds risk-based human intervention: routine reversible work may proceed automatically, while sensitive or irreversible actions require explicit checkpoints. [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 26–30) · [[raw/google-vibe-coding-agent-security-evaluation|Security and evaluation source record]] (pp. 18–26)

## Tension: discipline versus complexity

The Google papers describe substantial production harnesses, while Anthropic advises adding agentic complexity only when simpler designs fail. These are not necessarily contradictory: higher-risk autonomous coding requires stronger controls, but a low-risk, bounded task may not justify the complete architecture. [[raw/google-new-sdlc-vibe-coding|New SDLC source record]] · [[raw/anthropic-building-effective-agents|Anthropic source record]]

**Analysis:** Harness investment should scale with autonomy, permissions, reversibility, and consequence—not with enthusiasm for agentic architecture.

## Evidence status

Confidence is **medium** for the broad claim that agent-generated work shifts engineering effort toward context, verification, and governance. The sources are mutually consistent practitioner whitepapers from one organizational ecosystem, not independent controlled studies. Their labels and economic framing should be treated as useful models to test, not universal laws.

## Related

- [[concepts/ai-agents|AI agents]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/spec-driven-development|Spec-driven development]]
- [[concepts/agent-evaluation|Agent evaluation]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
