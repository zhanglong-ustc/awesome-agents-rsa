# Awesome Agents in Recommendation, Search & Ads

[![Website](https://img.shields.io/badge/Website-Explore_the_collection-1e6b4f?style=flat-square)](https://zhanglong-ustc.github.io/awesome-agents-rsa/)
[![GitHub Pages](https://github.com/zhanglong-ustc/awesome-agents-rsa/actions/workflows/pages.yml/badge.svg)](https://github.com/zhanglong-ustc/awesome-agents-rsa/actions/workflows/pages.yml)

A curated collection of papers, industry reports, and resources on **LLM-based Agents applied to Recommender Systems, Search, and Advertising** — covering planning, memory, tool use, trajectory-level RL, and production deployments.

**Scope:** Strictly limited to works published or first appearing on arXiv between **January 2025 and September 2026**. Earlier representative works are listed in the [Background & Boundaries](#background--boundaries) section.

**Agent Criterion:** A paper must exhibit at least one of: planning / multi-step decision, memory, tool use, environment interaction, reflection, multi-agent orchestration, or trajectory-level RL. Plain LLM rerankers or generative recommendation models without agentic loops are excluded.

**Ordering.** Entries are sorted by year in descending order. Within the same year, peer-reviewed publications are listed before arXiv preprints, and entries within each group are ordered by publication date in descending order.

Paper metadata is maintained in [`data/papers.json`](data/papers.json). After editing it, run `node scripts/generate-readme.mjs` to update this README.

## Contents

* [Recommender Systems](#recommender-systems)
* [Search](#search)
* [Advertising](#advertising)
* [Industry Deployments](#industry-deployments)
* [Background & Boundaries](#background--boundaries)
* [Trends & Takeaways](#trends--takeaways)
* [Selection Criteria](#selection-criteria)
* [Contributing](#contributing)

---

## Recommender Systems

Papers on LLM agents for recommendation: proactive recommendation, user-side agents, persona modeling, conversational recommendation, tool use, and structured memory.

{{TABLE:recommender-systems}}

---

## Search

Papers on LLM agents for information retrieval: interactive query understanding, reasoning reranking, iterative retrieval, and retrieval-focused RL.

{{TABLE:search}}

---

## Advertising

Papers on LLM agents for advertising: keyword management, campaign optimization, and contextual bandit policies.

{{TABLE:advertising}}

---

## Industry Deployments

Production-deployed or extensively A/B-tested agent systems from major platforms (2025–2026).

{{TABLE:industry-deployments}}

---

## Background & Boundaries

The following works were published **before January 2025** and are listed as background only — not included in the main tables.

| Year | Paper | Venue | Why Relevant |
|------|-------|-------|--------------|
| 2024 | [AgentCF: Collaborative Learning with Autonomous Language Agents for Recommender Systems](https://dl.acm.org/doi/10.1145/3589334.3645537) | WWW 2024 | Puts cross-user collaborative signals into autonomous language-agent interaction; direct predecessor of PersonaX, MemRec, and collaborative semantic memory works. |
| 2024 | [MACRec: A Multi-Agent Collaboration Framework for Recommendation](https://dl.acm.org/doi/10.1145/3626772.3657686) | SIGIR 2024 | Early representative multi-agent role collaboration for recommendation; direct background of TAIRA and 2025 multi-agent recommenders. |
| 2024 | [RecMind: Large Language Model Powered Agent for Recommendation](https://aclanthology.org/2024.findings-naacl.176) | NAACL Findings 2024 | Important early work on planning/tool-use paradigm for LLM recommender agents; 2025–2026 works like T-PRA, AgenticRec, MARS continue on longer horizons, stronger memory, and trainable tool policy. |

---

## Trends & Takeaways

### 2025 → 2026 Shift

**2025 main line:** LLM as recommendation interaction decision layer — proactive recommendation emphasizes long-horizon feedback (T-PRA), user-side state and profile (iAgent, PersonaX), multi-turn dialogue and multi-agent planning (ECPO, TAIRA).

**2026 shift:** Agent post-training + structured memory + active tool use — AgenticRec directly optimizes tool-use trajectories via RL; MemRec/MARS structure long-term memory with lifecycle management; CoVeMem makes collaborative memory differentiable and candidate-retrievable. AgentMMRec and EvoRec widen that transition from user/item knowledge integration to multi-agent model-development loops with persistent experiment memory. CORAL and DMRL then move the loop into live recommender and advertising control, where measured A/B outcomes become the state for the next decision.

### Three Clear Trends

1. **Recommendation agents**: The center of gravity has moved from one-shot LLM ranking to persistent state, active evidence acquisition, and explicit user/agent interaction. CoVeMem makes collaborative memory trainable by ranking gradients, while MMEACR and AgentMMRec coordinate user/item reasoning with multimodal or graph-structured evidence. RecThinker adds an Analyze→Plan→Act loop whose SFT+GRPO policy learns which recommendation-specific tools to call. AgentCom and EvoRec extend the same direction to cross-user communication skills and reusable success/failure experience across recommender-development rounds. CORAL, A/B Agent, and RecSys Factory expand the boundary again—from serving recommendations to continually operating and improving live systems through measured, budgeted, and auditable decisions.
2. **Search agents**: Search is becoming a trajectory-control problem rather than a query-rewrite module. CAFE and CAS optimize when to seek feedback, how much evidence to retrieve, and how complete trajectories enter RL, while ReTree and LoongReflect make reflection a reversible memory-control action. NIS-Agent and Marco DeepResearch isolate or independently verify evidence before it contaminates long-horizon context; SciLENS brings the same planning-and-verification loop to a fully local 12-million-paper environment. Agentic-R co-trains the retriever with the search policy instead of treating retrieval as fixed. Headroom-Drift and SignBalance now target the optimization layer itself, controlling replay staleness and removing guess-driven GRPO advantage from multi-turn search trajectories.
3. **Advertising and industrial control**: Agents increasingly operate above low-latency serving as planners, controllers, and experiment-driven policy selectors. AdsWorldEngine co-evolves a conversational-ad Orchestrator and its tools, while HOBA, SWAG-Bid, LangBP, and AIGB-R1 decompose long-horizon bidding into strategic planning and fast execution. DMRL makes the control document itself trainable: an upper agent edits skills, a bounded lower agent applies parameters, and delayed A/B outcomes assign edit-level credit. AB-GRPO shows that group-relative trajectory optimization also transfers to constrained campaign pacing, although its evidence remains offline; Astar and A/B Agent close longer engineering and experimentation loops with experience write-back. Across these systems, online experiments increasingly provide the environment signal, while whitelists, budget projection, constrained action spaces, and human review contain operational risk.

### Convergence of Four Research Lines

Planning · Memory · Tool Use · RL are converging in 2026: AgenticRec and Agentic-R connect tool/retrieval trajectories to outcome reward; MARS, CoVeMem, and AgentMMRec turn memory into managed or trainable state; Marco and SciLENS couple evidence navigation with verification; CORAL, DMRL, Astar, and A/B Agent extend the same loop to live industrial configuration and strategy iteration.

### Open Problems

- Can ranking/business reward directly train the full agent trajectory end-to-end?
- Can memory evolve from static history to lifecycle belief state without drift?
- Can agents autonomously judge when and which retrieval/recommendation tools to use?
- Can industrial systems transition from demos to self-iterating production control systems via constrained actions, verification, rollback, and online experiments?

---

## Selection Criteria

This repository includes papers that meet one or more of the following criteria:

* Directly study LLM agents for recommendation, search, or advertising with clear agentic properties
* Propose methods for memory, tool use, multi-agent orchestration, or trajectory-level RL in RS/Search/Ads
* Document production deployments with online A/B evidence
* Offer important insights from agentic planning, reasoning, or self-improvement in information systems

## 💡 Contributing

### Contributing to this repository

🙌 Have we missed any important papers, deployments, or resources? Contributions are welcome!

When suggesting a paper, please include:

* Paper title and authors
* Venue or arXiv link
* Code or project link, if available
* A short one-sentence description of the core **agentic** contribution
* Both Chinese and English abstracts (for the interactive website detail panel)

Entry format:
```json
{
  "year": 2026,
  "title": "Paper Title",
  "paperUrl": "https://arxiv.org/abs/XXXX.XXXXX",
  "venue": "ACL 2026",
  "resource": { "label": "Code", "url": "https://github.com/..." },
  "trainingMethods": ["SFT", "RL"],
  "tags": ["Memory", "Tool Use"],
  "description": "One-sentence description of the core agentic mechanism.",
  "detailId": "unique-id",
  "details": {
    "abstractZh": "中文摘要...",
    "abstractEn": "English abstract..."
  }
}
```

### Contributors

<a href="https://github.com/zhanglong-ustc/awesome-agents-rsa/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=zhanglong-ustc/awesome-agents-rsa" />
</a>
