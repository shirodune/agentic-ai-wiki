---
title: "ReAct: Synergizing Reasoning and Acting in Language Models"
type: source
tags: [agents, reasoning, tools, evaluation]
sources: []
updated: 2026-07-14
publish: true
source_url: https://react-lm.github.io/
accessed: 2026-07-14
redistribution: link-summary-only
---

# ReAct: Synergizing Reasoning and Acting in Language Models

## Source metadata

- **Authors:** Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik Narasimhan, and Yuan Cao
- **Format:** Research project page
- **Project page:** [react-lm.github.io](https://react-lm.github.io/)
- **Paper:** [arXiv:2210.03629](https://arxiv.org/abs/2210.03629)
- **Code:** [ysymyth/ReAct](https://github.com/ysymyth/ReAct)

## Original summary

ReAct is a prompting and trajectory format that interleaves language-model reasoning traces with task-specific actions and observations from an external environment. Reasoning is used to maintain and revise plans, while actions retrieve information or change the environment; resulting observations then ground subsequent steps.

The project page reports experiments in question answering, fact verification, embodied decision-making, and online shopping. It attributes improved factual grounding and inspectable task trajectories to the combination of reasoning and acting. It reports absolute success-rate improvements of 34 percentage points on ALFWorld and 10 percentage points on WebShop over the comparison methods used in the paper, with one or two in-context examples.

The page also shows failure cases and argues that the explicit trajectory format makes behavior easier to inspect and correct. It describes early fine-tuning results as promising but preliminary.

## Important claims

- Interleaving reasoning, actions, and observations allows plans to be updated using external feedback.
- Action-only behavior may lack synthesis, while reasoning without external interaction may propagate unsupported internal assumptions.
- The project reports gains on the specific benchmarks and baselines evaluated in the associated paper.
- Explicit task trajectories can aid human inspection, though inspectability is not itself proof of correctness.

## Limitations and provenance notes

The project page is an author-produced summary of the associated research, not an independent replication. Reported gains are benchmark- and baseline-specific and should not be generalized to all agents or environments without additional evidence. The page's fine-tuning discussion is explicitly framed as initial results.

This source record covers the project page supplied for ingestion. The linked paper should be ingested separately before making detailed claims about methods, experimental controls, or statistical reliability.

The copyright status of the project-page prose does not clearly permit republication, so this record preserves only metadata, an original summary, and links.

## Related pages

- [[concepts/react|ReAct]]
- [[concepts/ai-agents|AI agents]]
- [[concepts/agent-tools|Agent tools]]
- [[concepts/agent-safety-and-control|Agent safety and control]]
