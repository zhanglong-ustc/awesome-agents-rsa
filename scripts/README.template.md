# Awesome Agents in Recommendation, Search & Ads

[![Website](https://img.shields.io/badge/Website-Explore_the_collection-1e6b4f?style=flat-square)](https://zhanglong-ustc.github.io/awesome-agents-rsa/)
[![GitHub Pages](https://github.com/zhanglong-ustc/awesome-agents-rsa/actions/workflows/pages.yml/badge.svg)](https://github.com/zhanglong-ustc/awesome-agents-rsa/actions/workflows/pages.yml)

A curated collection of papers, industry reports, and resources on **LLM-based Agents applied to Recommender Systems, Search, and Advertising** — covering planning, memory, tool use, trajectory-level RL, and production deployments.

**Scope:** Strictly limited to works published or first appearing on arXiv between **January 2025 and August 2026**. Earlier representative works are listed in the [Background & Boundaries](#background--boundaries) section.

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

**2026 shift:** Agent post-training + structured memory + active tool use — AgenticRec directly optimizes tool-use trajectory via RL; MemRec/MARS structure long-term memory with lifecycle management; ReasonRec lets the model autonomously decide when to invoke tools based on uncertainty.

### Three Clear Trends

1. **Recommendation agents**: From "LLM as decision-maker" → "stateful, trainable, tool-using long-horizon decision systems"
2. **Search agents**: Core moves beyond "LLM rewrites query" → closed loop of query understanding + iterative retrieval + corpus feedback + reasoning rerank, with RL directly optimizing retrieval/ranking reward
3. **Industrial systems**: "Agent on the control plane, proven models on the data plane" — Agent for strategy iteration, query expansion, push scheduling; traditional high-throughput models continue large-scale candidate generation and low-latency scoring

### Convergence of Four Research Lines

Planning · Memory · Tool Use · RL are converging in 2026: AgenticRec connects tool-use trajectory to final ranking reward; MARS/MemRec solve long-term state management; ReasonRec solves "when to invoke tools"; STEPS extends planning to the time of next system invocation.

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
