---
title: Spec-Driven Development
type: concept
tags: [agents, development, specifications, evaluation, safety]
sources:
  - raw/google-spec-driven-production-development.md
updated: 2026-07-14
publish: true
---

# Spec-Driven Development

Spec-driven development (SDD) is an [[concepts/agentic-engineering|agentic engineering]] practice in which a reviewed, versioned specification becomes the shared source of truth for humans and coding agents before implementation. The aim is to reduce model guessing by making architecture, behavior, and acceptance criteria explicit. [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 7–12)

## Specification contents

The Google whitepaper recommends covering:

- goals, non-goals, and rationale;
- architecture and component boundaries;
- data models and API contracts;
- required technologies and version constraints;
- expected user-visible behavior;
- acceptance criteria, error cases, and edge cases;
- security, privacy, and operational constraints;
- diagrams or examples where they remove ambiguity.

A specification is usually versioned with the project so the [[concepts/agent-harnesses|agent harness]], reviewers, and implementation share a common artifact. [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 8–12)

## Behavioral specifications

Behavior-driven scenarios express preconditions, actions, and expected outcomes, often through Given–When–Then structure. They can connect natural-language intent to executable acceptance tests. [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 9–10)

**Analysis:** Behavioral examples are strongest when paired with invariants and non-functional requirements. Passing a small scenario set does not establish security, performance, accessibility, or correctness outside those cases.

## Instruction hierarchy

Specifications coexist with repository instructions, local task prompts, skills, tool definitions, and organizational policies. Their precedence and scope should be explicit; dumping every rule into one prompt can increase context competition rather than clarity. [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 11–15) · [[concepts/agent-skills|Agent skills]]

## Verification and change control

The specification should inform [[concepts/agent-evaluation|evaluation]] and review, not substitute for them. When requirements change, the spec, tests, and implementation must be reconciled deliberately. Small changes and risk-based approval reduce the chance that reviewers face an unmanageable volume of generated code. [[raw/google-spec-driven-production-development|Spec-driven development source record]] (pp. 18–30)

## Tensions and limitations

- A detailed but wrong specification can make an agent reliably build the wrong system.
- Specifications can become stale or conflict with existing behavior and undocumented constraints.
- Re-generating code is not costless when systems carry data migrations, external integrations, audit history, or compatibility obligations.
- Format-sensitive performance claims may depend on model, task, and evaluation setup.
- Excessive detail can consume context and hide the most important constraints.
- Agent-generated tests can repeat the implementation's mistaken assumptions unless independent evidence supplies a stronger oracle.
- Placeholder substitution and regular expressions are narrow input-processing tools, not comprehensive prompt-injection or privacy defenses.

The source's quantitative claims about instruction formats come from a separate cited study and remain unverified in this wiki.

## Evidence status

Confidence is **medium** that explicit, reviewed specifications reduce ambiguity and improve testability. Confidence is **low-to-medium** for claims that code becomes broadly disposable or that one document format is generally optimal.

## Related

- [[concepts/agentic-engineering|Agentic engineering]]
- [[concepts/agent-harnesses|Agent harnesses]]
- [[concepts/agent-evaluation|Agent evaluation]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
- [[concepts/agent-skills|Agent skills]]
