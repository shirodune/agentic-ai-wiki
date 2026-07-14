---
title: ReAct
type: concept
tags: [agents, reasoning, tools, evaluation]
sources:
  - raw/react-synergizing-reasoning-and-acting.md
updated: 2026-07-14
publish: true
---

# ReAct

ReAct is a prompting and trajectory format that interleaves language-model reasoning with actions and observations from an external environment. It connects planning to [[concepts/agent-tools|tool]] feedback instead of treating reasoning and acting as separate phases. [[raw/react-synergizing-reasoning-and-acting|ReAct source record]]

## Cycle

A ReAct trajectory alternates among:

1. **reasoning**, which forms or updates a plan;
2. **action**, which queries or changes an environment;
3. **observation**, which returns external information for the next step.

The format is an explicit instance of the feedback loop used by [[concepts/ai-agents|AI agents]]. It can be embedded within a broader [[concepts/agent-orchestration|orchestration]] design. [[raw/react-synergizing-reasoning-and-acting|ReAct source record]]

## Reported findings

The project page reports applications to HotpotQA, FEVER, ALFWorld, and WebShop. It says interaction with a Wikipedia API reduced hallucination and error propagation relative to chain-of-thought-only baselines on question answering and fact verification. It reports absolute success-rate improvements of 34 percentage points on ALFWorld and 10 percentage points on WebShop over the evaluated imitation- and reinforcement-learning methods, using one or two in-context examples. [[raw/react-synergizing-reasoning-and-acting|ReAct source record]]

The page also contrasts reasoning-only and action-only failures and presents explicit trajectories as easier for humans to inspect and correct. Its fine-tuning results are described as initial rather than conclusive. [[raw/react-synergizing-reasoning-and-acting|ReAct source record]]

## Interpretation

**Evidence:** The project page supports the claim that ReAct outperformed the specified baselines on the reported benchmark settings.

**Analysis:** It does not establish that visible reasoning is always faithful, that ReAct is universally better than later agent methods, or that benchmark gains transfer directly to production. Inspectability should therefore be treated as a debugging aid within [[concepts/agent-safety-and-control|agent safety and control]], not as proof of trustworthy behavior.

## Limitations

This page currently relies on the project website and its abstract-level summary. Detailed assessment of experimental controls, prompts, ablations, and statistical uncertainty requires separate ingestion of the linked paper. The results are author-reported and have not yet been paired in this wiki with an independent replication.

## Evidence status

Confidence is **medium** for the project page's benchmark-specific account and **low** for broader generalization beyond those experiments.

## Related

- [[concepts/ai-agents|AI agents]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-orchestration|Agent orchestration]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
