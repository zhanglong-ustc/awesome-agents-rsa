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

**2026 shift:** Agent post-training + structured memory + active tool use — AgenticRec directly optimizes tool-use trajectories via RL; MemRec/MARS structure long-term memory with lifecycle management; CoVeMem makes collaborative memory differentiable and candidate-retrievable. AtomRec and HyperTrace now make memory revision more granular and uncertainty-aware, while AGAS shows that the same persistent, reflective coordination creates a recommender attack surface. ITER shifts retriever training from isolated queries to interaction histories, and IGPO/AutoLR move policy memory, experiment evidence, and human-gated decisions into commercial search and recommender operations.

### Three Clear Trends

1. **Recommendation agents**: The center of gravity has moved from one-shot LLM ranking to persistent state, active evidence acquisition, and explicit user/agent interaction. CoVeMem makes collaborative memory trainable by ranking gradients, while MMEACR and AgentMMRec coordinate user/item reasoning with multimodal or graph-structured evidence. AtomRec evolves field-level atomic memories and cross-user evidence paths, while HyperTrace preserves competing preference hypotheses instead of collapsing ambiguity into one profile. RecThinker, AgentCom, and EvoRec extend the same direction to learned tool policies, cross-user communication, and experiment memory across recommender-development rounds. AGAS adds a security warning: reflective multi-agent memory can coordinate shilling as effectively as benign recommendation.
2. **Search agents**: Search is becoming a trajectory-control problem rather than a query-rewrite module. MOSAIC adapts graph exploration per query, while VikingRAG combines hierarchical tools, reusable experience edges, and evidence-sufficiency-triggered escalation. CAFE and CAS optimize when to seek feedback and how complete trajectories enter RL; ReTree and LoongReflect make reflection a reversible memory-control action; ITER and Beyond One-Shot Expansion use interaction history and unresolved evidence to drive the next retrieval step. SearchAtlas makes those strategies inspectable as evidential query graphs, while Agentic Share-of-Search applies coordinator, extraction, and diagnostic agents to LLM-mediated commerce visibility. RAP, NIS-Agent, SciLENS, and HAE-GEO further make temporal controls, evidence isolation, verification, and recovery first-class trajectory events.
3. **Advertising and industrial control**: Agents increasingly operate above low-latency serving as planners, controllers, and experiment-driven policy selectors. AdsWorldEngine co-evolves a conversational-ad Orchestrator and its tools, while HOBA, SWAG-Bid, LangBP, and AIGB-R1 decompose long-horizon bidding into strategic planning and fast execution. DMRL makes the control document itself trainable, and AB-GRPO transfers group-relative trajectory optimization to constrained campaign pacing, though its evidence remains offline. IGPO grounds commercial AI-search policies in live inventory and replay-validated guidelines, while AutoLR turns recommender R&D evidence into human-gated launch candidates. Across these systems, online experiments provide the environment signal while whitelists, budget projection, constrained actions, replay validation, and human review contain operational risk.

### Convergence of Four Research Lines

Planning · Memory · Tool Use · RL are converging in 2026: AgenticRec, Agentic-R, and ITER connect tool/retrieval trajectories to outcome-sensitive learning; MARS, CoVeMem, AtomRec, and HyperTrace turn memory into managed, trainable, or hypothesis-preserving state; MOSAIC, VikingRAG, SearchAtlas, SciLENS, and HAE-GEO couple adaptive evidence navigation with reuse, verification, and trajectory diagnosis; CORAL, DMRL, IGPO, AutoLR, Astar, and A/B Agent extend the same loop to live industrial configuration and strategy iteration.

### Open Problems

- Can ranking/business reward directly train the full agent trajectory end-to-end?
- Can memory evolve from static history to lifecycle belief state without drift?
- Can agents autonomously judge when and which retrieval/recommendation tools to use?
- Can persistent recommender and search memories remain robust to poisoning, strategic users, and irreversible profile drift?
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
