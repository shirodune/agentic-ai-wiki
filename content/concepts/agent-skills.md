---
title: Agent Skills
type: concept
tags: [agents, skills, memory, tools, evaluation]
sources:
  - raw/google-agent-skills.md
  - raw/google-agent-tools-interoperability.md
  - raw/karpathy-llm-wiki.md
updated: 2026-07-14
publish: true
---

# Agent Skills

Agent skills are portable, on-demand packages of procedures and supporting resources that give a general-purpose [[concepts/ai-agents|AI agent]] specialist competence. In the Google whitepaper, a skill is a folder anchored by `SKILL.md`, with optional scripts, references, and assets. [[raw/google-agent-skills|Agent Skills source record]] (pp. 7–12)

## Progressive disclosure

Skills use staged loading to manage context:

1. metadata such as name and description is available for routing;
2. the instruction body loads when the skill triggers;
3. references and assets load only when required;
4. scripts can perform deterministic work without placing their implementation in the model context.

This makes the description a routing contract rather than simple documentation. Under-triggering makes a skill unavailable; over-triggering injects irrelevant context. [[raw/google-agent-skills|Agent Skills source record]] (pp. 10–24)

## Architectural distinction

| Primitive                | Main purpose                                    | Typical loading or invocation                  |
| ------------------------ | ----------------------------------------------- | ---------------------------------------------- |
| Skill                    | Reusable procedural guidance and resources      | Selected on demand from metadata               |
| Tool                     | Read or change external state                   | Invoked through a defined function or protocol |
| MCP server               | Standardized exposure of tool capabilities      | Connected through an MCP client                |
| Project instruction file | Persistent repository or project guidance       | Loaded by the host according to local rules    |
| Specialized agent        | Independent model-driven role with its own loop | Delegated to through orchestration or A2A      |

The boundaries can overlap: a skill may call tools, ship scripts, or instruct an agent to delegate. [[raw/google-agent-skills|Agent Skills source record]] (pp. 11–14) · [[raw/google-agent-tools-interoperability|Tools and interoperability source record]] (pp. 6–10)

## Evaluation

A skill should be evaluated at multiple levels: trigger behavior, final output, tool trajectory, policy compliance, latency or token cost, and interaction with other installed skills. Testing only the skill in isolation can miss routing conflicts and context competition in the actual [[concepts/agent-harnesses|agent harness]]. [[raw/google-agent-skills|Agent Skills source record]] (pp. 15–31)

The source's apparently conflicting advice can be reconciled as a two-stage process: isolate one skill to diagnose its trigger and behavior, then test it again with the realistic co-loaded library and shared token budget. No fixed 5,000-token or 5,000-word threshold should be treated as universal. [[raw/google-agent-skills|Agent Skills source record]] (pp. 21–31, 43–50)

See [[concepts/agent-evaluation|Agent evaluation]] for methods and evidence limits.

## Composition and deterministic logic

The whitepaper recommends explicit composition structures such as directed acyclic graphs for predictable dependencies. It also argues for “shifting intelligence left”: move deterministic parsing, calculations, and formatting from long prompts into testable scripts. [[raw/google-agent-skills|Agent Skills source record]] (pp. 36–41)

**Analysis:** This can reduce prompt ambiguity but increases software supply-chain and permission concerns. Skill packages should be versioned, reviewed, permission-scoped, and tested like code when they contain executable scripts.

## Meta-skills

Meta-skills can propose, generate, or revise other skills from successful trajectories. The source warns that self-improvement is only as sound as its evaluation objective and governance. An agent may optimize a weak proxy or introduce unsafe instructions if changes are accepted automatically. [[raw/google-agent-skills|Agent Skills source record]] (pp. 32–35)

## Knowledge-maintenance procedures

Karpathy's [[concepts/llm-wiki-pattern|LLM Wiki pattern]] uses a schema to encode recurring ingest, query, and lint behavior. **Analysis:** A host can implement this as project instructions, an always-loaded schema, or an on-demand skill. Packaging changes loading and portability, but not the need for source approval, provenance, tests, and human review. [[raw/karpathy-llm-wiki|Karpathy LLM Wiki source record]]

## Evidence status

Confidence is **medium** for the architecture and evaluation checklist. Claims of cross-platform standardization and skills as a dominant unit of agent improvement are still emerging industry judgments. Host-specific activation, packaging, and security behavior limits portability.

## Related

- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-interoperability|Agent interoperability]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-evaluation|Agent evaluation]]
- [[concepts/agent-orchestration|Agent orchestration]]
