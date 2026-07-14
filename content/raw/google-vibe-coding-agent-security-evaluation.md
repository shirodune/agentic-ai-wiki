---
title: Vibe Coding Agent Security and Evaluation
type: source
tags: [agents, safety, security, evaluation, observability]
sources: []
updated: 2026-07-14
publish: true
source_url: https://www.kaggle.com/whitepaper-vibe-coding-agent-security-and-evaluation
accessed: 2026-07-14
redistribution: link-summary-only
---

# Vibe Coding Agent Security and Evaluation

## Source metadata

- **Authors:** Sokratis Kartakis, Aron Eidelman, Wafae Bakkali, and Meltem Subasioglu
- **Publisher:** Google via Kaggle
- **Date:** May 2026
- **Length:** 41 pages
- **Kaggle page:** [Vibe Coding Agent Security and Evaluation](https://www.kaggle.com/whitepaper-vibe-coding-agent-security-and-evaluation)
- **Official PDF:** [Google Drive](https://drive.google.com/file/d/1kEtWZmFMTGYqe12jMiZPOi9zYcyFXfHF/view)

## Original summary

The paper separates **security**, which asks whether an agent stayed within authorized boundaries, from **evaluation**, which asks whether the work produced inside those boundaries is worth shipping. It argues that autonomous coding systems require continuous, context-sensitive trust rather than a one-time identity check (pp. 6–9).

Its proposed seven-pillar security architecture covers infrastructure and networking, data, model behavior, application and runtime controls, identity and access management, observability and incident response, and governance. Recommended controls include ephemeral sandboxes, restricted network egress, tenant-isolated memory, protected instructions, lifecycle hooks, agent gateways, unique workload identities, attribute-based authorization, and just-in-time token downscoping (pp. 9–19).

The threat model includes supply-chain poisoning, hallucinated packages, prompt injection, repository poisoning, MCP spoofing, confused-deputy behavior, lateral movement, sensitive-data leakage, and unintended high-impact actions. Red, blue, and “green” teaming are proposed for attacking, detecting, quarantining, and repairing agent behavior (pp. 13–26).

For evaluation, the paper proposes seven dimensions spanning intent satisfaction, functional correctness, code quality, safety, efficiency, trajectory quality, and adaptability. It recommends combining deterministic tests, static analysis, model-based judges, human review, adversarial testing, and trace analysis rather than relying on one score (pp. 27–39).

## Important claims

- Valid credentials do not imply that an autonomous action is appropriate for the user's current intent.
- Agent security should be externally enforced by the harness because the underlying model may fail or be compromised.
- Least privilege must account for user, intent, time, and tool context rather than only static roles.
- Evaluation should inspect both final artifacts and the trajectory that produced them.
- Observability is required for debugging and evaluation, but retained traces create their own privacy and security obligations.

## Limitations and provenance notes

The seven-pillar architecture and “effective trust” framing are author-proposed frameworks, not formally validated standards. Many controls are established security practices adapted to agents, while some terminology and product references are Google-specific. The paper provides architectural guidance and examples rather than comparative deployment evidence showing that the complete framework reduces incidents.

Model-based evaluation can inherit model bias, judge instability, and blind spots. Trace access improves diagnosis but does not make internal explanations faithful or guarantee correctness.

The document contains unresolved internal tensions. Its detailed identity section favors dedicated agent identities rather than delegated human credentials, while its recap calls for delegated user identities. It says users may be unable to validate outputs yet also treats humans as the only ground truth for intent; it recognizes that intent changes during a session but proposes deriving a rubric from the opening messages. Finally, containment cannot prove that an agent “did no harm,” and autonomous remediation should not bypass the paper's own human-consent requirements for high-risk actions.

The copyright status does not clearly permit republication of the PDF, so this record contains only metadata, an original summary, and links.

## Related pages

- [[concepts/agent-safety-and-control|Agent safety and control]]
- [[concepts/agent-evaluation|Agent evaluation]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agentic-engineering|Agentic engineering]]
