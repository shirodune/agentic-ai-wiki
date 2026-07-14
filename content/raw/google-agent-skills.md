---
title: Agent Skills
type: source
tags: [agents, skills, memory, evaluation, orchestration]
sources: []
updated: 2026-07-14
publish: true
source_url: https://www.kaggle.com/whitepaper-agent-skills
accessed: 2026-07-14
redistribution: link-summary-only
---

# Agent Skills

## Source metadata

- **Authors shown in the PDF:** Tanvi Singhal, Gabriela Hernandez Larios, Debanshu Dus, Lavi Nigam, and Smitha Kolan
- **Publisher:** Google via Kaggle
- **Date:** May 2026
- **Length:** 62 pages
- **Kaggle page:** [Agent Skills](https://www.kaggle.com/whitepaper-agent-skills)
- **Official PDF:** [Google Drive](https://drive.google.com/file/d/1Wso-CM4aAvTxFZa5wjBntKM3IVSg7PWW/view)

## Original summary

The paper defines an **Agent Skill** as a portable folder anchored by `SKILL.md`, with optional scripts, references, and assets. A skill supplies on-demand specialist procedures to a general-purpose agent. Its progressive-disclosure model keeps metadata available for routing, loads the instruction body only when triggered, and retrieves supporting resources only when needed (pp. 7–12).

Skills are positioned as a form of procedural memory: they preserve how to perform recurring work rather than only storing facts or past events. The paper distinguishes skills from tool protocols such as MCP and from always-loaded project instructions such as `AGENTS.md`; skills package reusable procedures, while protocols expose capabilities and project files provide persistent local guidance (pp. 11–14).

The evaluation framework treats activation as the first gate, then separately measures output quality and tool trajectory. It recommends testing positive and negative triggers, paraphrases, adversarial cases, resource use, policy compliance, and multi-skill context budgets. It warns that evaluating a skill alone can hide routing conflicts and context competition present in production (pp. 15–24).

For production, the paper discusses versioning, ownership, context overflow, meta-skills that propose or revise skills, composition through directed acyclic graphs, capability profiles, and moving deterministic logic from prompts into testable scripts (pp. 25–41).

## Important claims

- Progressive disclosure can provide specialist procedures without loading every instruction into every model call.
- A skill's description functions as a routing interface and must be evaluated for both under-triggering and over-triggering.
- Final-answer evaluation alone misses failures in tool choice, ordering, permissions, and recovery behavior.
- Skill evaluation should occur in realistic multi-skill environments because context competition can cause silent degradation.
- Self-modifying or meta-skills require strong evaluations and human governance to avoid optimizing weak proxy metrics.

## Limitations and provenance notes

This is a Google-authored practical whitepaper advocating an emerging convention. Cross-platform portability is incomplete: hosts can differ in installation paths, activation behavior, tool allowlists, and security controls. Claims that skills are becoming a standard or are a primary unit of improvement are directional industry judgments rather than settled empirical conclusions.

The Kaggle landing page spells one author's surname “Das,” while the PDF title page extracted on 2026-07-14 reads “Dus.” This record follows the PDF and preserves the discrepancy for review.

Specific production percentages and benchmark-style claims cited by the paper should be checked against their original references before being treated as independently verified evidence.

The paper also contains internal inconsistencies. It recommends a single-skill sub-agent for diagnosis but warns never to evaluate a skill purely in isolation; a defensible sequence is isolated diagnosis followed by full-library staging. It alternates between 5,000-token and 5,000-word size guidance, and reports marketplace counts with different scopes. Endnotes associated with “Lost in the Middle” and “Context Rot” appear to reuse URLs assigned to other references, so those citations should be verified before their claims are reused.

The copyright status does not clearly permit republication of the PDF, so this record contains only metadata, an original summary, and links.

## Related pages

- [[concepts/agent-skills|Agent skills]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-evaluation|Agent evaluation]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-harnesses|Agent harnesses]]
