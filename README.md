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

| Year | Paper                                                                                                                                                       | Venue             | Code                                                   | Type                                                                                      | Description                                                                                                                                                                                                                                                                         |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- | ------------------------------------------------------ | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2026 | [When Memory Takes Gradients: Collaborative Vector Memory for Agentic Recommender Systems](https://arxiv.org/abs/2608.26895)                                | arXiv 2026        | -                                                      | SFT + Vector Memory + Candidate Retrieval + Collaborative Signals + Long-History          | CoVeMem stores frozen LightGCN user/item states as persistent collaborative memory, retrieves candidate-conditioned history into LLM soft tokens, and trains a parametric reader with semantic alignment and masked listwise ranking.                                               |
| 2026 | [Conversational Recommendation over Live E-Commerce Catalogues with Self-Refreshing Retrieval](https://arxiv.org/abs/2608.27006)                            | RecSys 2026       | [Demo](https://github.com/infobip/infobip-agentic-crs) | Training-free + Conversational Rec + Tool Orchestration + Session Memory + Live Catalogue | A controller routes multi-turn shopping dialogue to preference elicitation or a search→rerank→diversity tool path, while a hash-based self-refreshing retriever keeps shared catalogue, profile, and session state current.                                                         |
| 2026 | [Personalized Communication Skills for Agentic Recommender Systems](https://arxiv.org/abs/2608.08417)                                                       | arXiv 2026        | -                                                      | Training-free + Multi-Agent + Skill Routing + Reflection + User Modeling                  | AgentCom routes target-user and advisor agents through a reusable why–what–how–who communication skill bank, then evolves the bank from failed interactions to repair missing preference evidence.                                                                                  |
| 2026 | [ReasonRec: A Reasoning-Augmented Multimodal Agent for Unified Recommendation](https://aclanthology.org/2026.findings-acl.391)                              | ACL Findings 2026 | -                                                      | SFT + RL + Multimodal + CoT + Tool Delegation + Uncertainty                               | Observe→Deliberate→Act multimodal recommender agent: VLM encoding, reasoning-aware instruction tuning, and uncertainty-triggered tool delegation to a lightweight external recommender.                                                                                             |
| 2026 | [Seeing and Reflecting: Multimodal Memory-Enhanced Agent Collaboration for Recommendation](https://arxiv.org/abs/2607.07108)                                | arXiv 2026        | -                                                      | Training-free + Multi-Agent + Multimodal Memory + Reflection + User Modeling              | MMEACR coordinates persistent User and Item Memory Agents with attribute-guided reinforcement/reflection, preserves raw cross-modal evidence in a parallel embedding memory, and fuses both rankings via reciprocal rank fusion.                                                    |
| 2026 | [MARS: Agentic Recommender System with Hierarchical Belief-State Memory](https://arxiv.org/abs/2605.14401)                                                  | arXiv 2026        | -                                                      | Training-free + Memory + Planning + Belief State + Long-horizon                           | Models recommendation as a partially observable problem; divides agent memory into event→preference→profile three-layer belief state with six explicit lifecycle operations managed by an LLM planner.                                                                              |
| 2026 | [MemRec: Collaborative Memory-Augmented Agentic Recommender System](https://arxiv.org/abs/2601.08816)                                                       | arXiv 2026        | -                                                      | Training-free + Collaborative Memory + Multi-LM + Graph + Async Propagation               | Reconstructs cross-user collaborative signals as a semantic memory graph; decouples memory management (lightweight LM_Mem) from reasoning and reranking (high-capability LLM_Rec) with asynchronous propagation.                                                                    |
| 2026 | [AgenticRec: Recommendation-Oriented Agentic Framework with Progressive Tool-Integrated Reasoning Optimization](https://arxiv.org/abs/2603.21613)           | arXiv 2026        | -                                                      | RL + ReAct + Tool Use + Trajectory RL + Ranking Reward                                    | Embeds recommendation-specific tools in a ReAct-style loop; trajectory-level RL with ranking reward trains the entire reasoning→tool invocation→observation→ranking chain; Progressive Preference Refinement mines hard negatives from ranking violations.                          |
| 2026 | [RecThinker: An Agentic Framework for Tool-Augmented Reasoning in Recommendation](https://arxiv.org/abs/2603.09843)                                         | arXiv 2026        | [Code](https://github.com/Aska-zhang/RecThinker)       | SFT + RL + Planning + Tool Use + Information Gaps + GRPO                                  | RecThinker runs an Analyze→Plan→Act investigation loop over five recommendation-specific tools, then uses self-augmented SFT and GRPO with accuracy, format, and tool-efficiency rewards to refine complete tool-use trajectories.                                                  |
| 2025 | [TAIRA: Thought-Augmented Planning for LLM-Powered Interactive Recommender Agent](https://arxiv.org/abs/2506.23485)                                         | arXiv 2025        | -                                                      | SFT + Multi-Agent + Planning + Thought Distillation                                       | Multi-agent interactive recommendation: a Manager Agent decomposes complex user intents into subtasks; Thought Pattern Distillation (TPD) extracts high-level thinking patterns from agent history and human expert experience to strengthen planning.                              |
| 2025 | [ECPO: Expectation Confirmation Preference Optimization for Multi-Turn Conversational Recommendation Agent](https://aclanthology.org/2025.findings-acl.307) | ACL Findings 2025 | -                                                      | SFT + RL + Multi-Turn CRA + Planning + Tool Use + Preference Optimization                 | Refines multi-turn conversational recommendation preference optimization to turn-level expectation confirmation; introduces AILO user agent simulating Activities/Interests/Language/Orientations; avoids expensive conversation-tree sampling via Backward Expectation Derivation. |
| 2025 | [PersonaX: A Recommendation Agent-Oriented User Modeling Framework for Long Behavior Sequence](https://aclanthology.org/2025.findings-acl.300)              | ACL Findings 2025 | -                                                      | Training-free + Persona + Long-History + Offline Cache + Memory                           | Solves context-length and latency bottlenecks by offline-clustering long behavior sequences into multi-persona profiles cached for online agent retrieval; using only 30–50% of behaviors improves AgentCF by 3–11% and Agent4Rec by 10–50%.                                        |
| 2025 | [iAgent: LLM Agent as a Shield between User and Recommender Systems](https://arxiv.org/abs/2502.14662)                                                      | ACL Findings 2025 | -                                                      | Training-free + User-Side Agent + Dynamic Memory + Reranking + Platform-User              | Places a user-side personal agent between user and platform; i²Agent adds instruction-aware parser and dynamic memory continuously reconstructing user profiles from feedback for reranking, achieving average +16.6% on ranking metrics vs EasyRec.                                |
| 2025 | [T-PRA: Tunable LLM-based Proactive Recommendation Agent](https://aclanthology.org/2025.acl-long.944)                                                       | ACL 2025          | -                                                      | SFT + RL + OPD + Proactive Rec + Actor-Advisor-Critic + Long-horizon + DPO                | Reformulates proactive recommendation as long-horizon sequential decision and influence path planning; Actor–Advisor–Critic structure with multi-objective long-term reward and DPO-style agent tuning via preference optimization.                                                 |

---

## Search

Papers on LLM agents for information retrieval: interactive query understanding, reasoning reranking, iterative retrieval, and retrieval-focused RL.

| Year | Paper                                                                                                                                   | Venue      | Code                                     | Type                                                                              | Description                                                                                                                                                                                                                                                     |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2026 | [CAFE: Self-Improving Search Agents Need Co-Evolving Feedback](https://arxiv.org/abs/2608.24794)                                        | arXiv 2026 | -                                        | RL + OPD + Iterative Search + Reflection + Critic + Trajectory Feedback           | A shared-parameter model alternates between search-agent and critic roles; online RL learns when feedback is worth requesting and how to use it, while rollout-matched preference optimization makes the critic co-evolve with the policy.                      |
| 2026 | [CAS: Conformalized Agentic Search via Adaptive Retrieval and Policy Weighting](https://arxiv.org/abs/2608.20771)                       | arXiv 2026 | [Code](https://github.com/S1llyBird/CAS) | RL + Iterative Search + Adaptive Retrieval + Conformal Prediction + Trajectory RL | CAS interleaves reasoning and search with conformal adaptive document sets, then uses online conformal confidence to down-weight unreliable complete trajectories inside GRPO.                                                                                  |
| 2026 | [Self-Correcting Long-Horizon Search Agents via Tree-Structured Memory](https://arxiv.org/abs/2608.10676)                               | arXiv 2026 | -                                        | Training-free + Tree Memory + Reflection + Error Recovery + Long-Horizon          | ReTree stores source-linked evidence and revision history in a bounded tree; contradictions trigger traceback, evidence replacement, summary regeneration, branch pruning, and resumed search.                                                                  |
| 2026 | [LoongReflect: Boosting Long-Horizon Reflection in Search Agents via Global Perspective Distillation](https://arxiv.org/abs/2608.11967) | arXiv 2026 | -                                        | SFT + RL + Reflection + Tree Memory + Backtracking + Trajectory RL                | LoongReflect treats reflection as memory control over a reversible trajectory tree; explicit reflect/backtrack actions are trained by answer-masked global-teacher distillation plus outcome-based GRPO with look-ahead coordination.                           |
| 2026 | [LegalMALR: Multi-Agent Query Understanding and LLM-Based Reranking for Chinese Statute Retrieval](https://arxiv.org/abs/2601.17692)    | arXiv 2026 | -                                        | RL + Multi-Agent + Query Rewrite + GRPO + Reasoning Rerank + Legal                | Multi-agent system reformulates implicit legal queries from multiple perspectives with iterative dense retrieval; GRPO-optimized MAS policy reduces randomness; LLM Reranker applies natural-language legal reasoning for statute applicability judgment.       |
| 2025 | [QAgent: A Modular Search Agent with Interactive Query Understanding](https://arxiv.org/abs/2510.08383)                                 | arXiv 2025 | -                                        | RL + Query Understanding + Multi-Step + Retrieval RL + Modular RAG                | Transforms query understanding from one-shot rewrite into interactive reasoning↔retrieval multi-step decision; modular pluggable design allows the RL-trained query-understanding agent to be inserted into existing search pipelines without full replacement. |
| 2025 | [REARANK: Reasoning Re-ranking Agent via Reinforcement Learning](https://arxiv.org/abs/2505.20046)                                      | arXiv 2025 | -                                        | RL + Listwise Rerank + Reasoning + Few-Shot + BRIGHT                              | Upgrades LLM reranker to a 'reason first, then listwise rank' agent; RL trains reasoning/ranking policy from only 179 annotated samples; REARANK-7B surpasses GPT-4 on the reasoning-intensive BRIGHT benchmark.                                                |

---

## Advertising

Papers on LLM agents for advertising: keyword management, campaign optimization, and contextual bandit policies.

| Year | Paper                                                                                                                                                        | Venue      | Code | Type                                                                           | Description                                                                                                                                                                                                                                                  |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | ---- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 2026 | [AdsWorldEngine: A Self-Evolving Conversational Advertising Agent through Orchestrator and Tool Coevolution](https://arxiv.org/abs/2608.13833)               | arXiv 2026 | -    | SFT + RL + Conversational Ads + Tool Coevolution + Reflection + Online A/B     | A gated advertising agent resolves dialogue state, generates commercial intents, calls retrieval/relevance/ranking tools, reflects over candidates, and alternates trajectory-level Orchestrator RL with preference updates to the tools themselves.         |
| 2026 | [Beyond Single-Episode Optimization: Sliding-Window Aware Generative Auto-Bidding for Long-Term Advertising Effectiveness](https://arxiv.org/abs/2607.25233) | arXiv 2026 | -    | SFT + Auto-Bidding + Hierarchical Planning + MPC + Long-Horizon                | SWAG-Bid couples an episode-level masked-trajectory planner with a step-level gated Decision Transformer to optimize every overlapping seven-day efficiency window rather than treating each day independently.                                              |
| 2026 | [HOBA: Hierarchical On-Policy Bidding Agents for Adaptive Online Advertising](https://arxiv.org/abs/2607.24779)                                              | KDD 2026   | -    | RL + Auto-Bidding + Reflection + Memory + Multi-Agent                          | Three-time-scale bidding control combines an LLM Think–Act–Observe–Reflect strategist with memory retrieval, a causal-adjusted SARSA expert selector, and a dynamic PID/MPC/IQL/Decision-Transformer expert pool.                                            |
| 2025 | [KP-Agent: Keyword Pruning in Sponsored Search Advertising via LLM-Powered Contextual Bandits](https://dl.acm.org/doi/10.1145/3746252.3760974)               | CIKM 2025  | -    | RL + Contextual Bandit + Keyword Pruning + Sponsored Search + Campaign Control | Models sponsored-search keyword pruning as an LLM-powered contextual bandit agent operating at the campaign/keyword control layer, learning policy via reinforcement signal to progressively refine keyword sets without entering millisecond-level serving. |

---

## Industry Deployments

Production-deployed or extensively A/B-tested agent systems from major platforms (2025–2026).

| Year | Paper                                                                                                                                                          | Venue                        | Code                                      | Type                                                                                            | Description                                                                                                                                                                                                                                                                                        |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- | ----------------------------------------- | ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2026 | [Shape Your Feed: An LLM-based Agentic System for Conversational Recommendation](https://arxiv.org/abs/2608.06632)                                             | RecSys 2026 Industrial Track | -                                         | SFT + OPD + Production Deployed + Conversational Rec + Memory + Multimodal Control              | Meta's three-flow system turns text, voice, and UI feedback into a persistent semantic profile, performs production-grounded agentic reranking/pruning, and self-evolves offline with SFT+DPO and judge ensembles.                                                                                 |
| 2026 | [STEPS: A Self-Triggered Agentic Push Recommendation System](https://arxiv.org/abs/2608.01949)                                                                 | arXiv 2026                   | -                                         | RL + Production Deployed + Push Rec + Self-Triggered + Long-horizon + 1B+ Users                 | Self-triggered push recommendation deployed to 1B+ Douyin users: Planning Agent decides next wake time via gated ordinal regression; Execution Agent decides send/no-send via trajectory reward; Filtering Agent cuts compute by 79.42%; results: active days +0.28%, disable rate -1.91%.         |
| 2026 | [Melo: A Production LLM-Powered Music Recommendation Agent](https://arxiv.org/abs/2607.23718)                                                                  | RecSys 2026                  | -                                         | Training-free + Production Deployed + Tool Orchestration + Reflection + Online A/B              | NetEase Cloud Music's production agent uses a deterministic Understand→Plan→Execute→Reflect→Synthesize graph, live-index entity grounding, and a bounded Reflect→Plan retry loop over heterogeneous retrieval and ranking tools.                                                                   |
| 2026 | [SR-Agent: Experience-Driven Agentic Framework for Post-Ranking Strategies Refinement in E-Commerce Recommendation](https://arxiv.org/abs/2607.17719)          | arXiv 2026                   | -                                         | RL + Production Deployed + Post-Ranking + Multi-Agent + Constrained Actions + Reward Gate       | Automates Kuaishou e-commerce post-ranking inspection/diagnosis/tuning: UserSim Agent finds bad cases, Analysis Agent compresses into structured diagnosis, Strategy Harness enforces bounded actions with multi-stage reward gates; 1-month A/B: orders +0.71%, depth +0.34%, diversity +0.48%.   |
| 2026 | [AgentX: Towards Agent-Driven Self-Iteration of Industrial Recommender Systems](https://arxiv.org/abs/2606.26859)                                              | arXiv 2026                   | -                                         | RL + Production Deployed + Self-Iteration + Multi-Agent + SGPO + A/B Loop                       | Multi-agent system automating algorithm iteration at Kuaishou: Brainstorm/Developing/Evaluation agents cover hypothesis→code→A/B→attribution; SGPO converts execution trajectories into semantic-gradient experience for harness self-improvement.                                                 |
| 2026 | [LEAPS: An LLM-Empowered Adaptive Plugin for Taobao AI Search](https://arxiv.org/abs/2601.05513)                                                               | arXiv 2026                   | -                                         | SFT + RL + Production Deployed + Query Expansion + Relevance Verification + Non-invasive Plugin | Broaden-and-Refine agentic plugin at both ends of Taobao AI Search pipeline: upstream Query Expander (diversity-aware RL) generates complementary queries; downstream Relevance Verifier (OCT + CoT reasoning) filters noise. Fully deployed since Aug 2025, serving hundreds of millions monthly. |
| 2026 | [SIRA: Superintelligent Retrieval Agent — The Next Frontier of Agentic Retrieval](https://ai.meta.com/research/publications/superintelligent-retrieval-agent/) | Meta Research 2026           | -                                         | Training-free + Corpus-Aware + Sparse Retrieval + Evidence Terms + Tool Use                     | Compresses multi-round exploratory search into one corpus-discriminative retrieval action: offline document enrichment, query-side evidence-term prediction using corpus statistics as tool calls; BrowseComp-Wikipedia Recall@1/10/100 = 9.70%/15.27%/36.14% over 25.6M docs.                     |
| 2025 | [PaSa: An LLM Agent for Comprehensive Academic Paper Search](https://arxiv.org/abs/2501.10120)                                                                 | arXiv 2025                   | [Code](https://github.com/bytedance/PaSa) | RL + Academic Search + Tool Use + Citation Chain + Search Policy                                | Full search agent continuously calling search tools, reading papers, following citation chains, judging relevance; RL-trained on 35K synthetic queries. PaSa-7B: Recall@20 +37.78%, Recall@50 +39.90% vs Google+GPT-4o paraphrasing.                                                               |
| 2025 | [MAAQR: An LLM-based Multi-Agent Framework for Adaptive Query Rewriting in Alipay Search](https://dl.acm.org/doi/10.1145/3726302.3731950)                      | SIGIR 2025                   | -                                         | SFT + Production Deployed + Query Rewriting + Multi-Agent + Online A/B                          | Splits Alipay search query rewriting into multi-agent adaptive decision for complex QA and few-recall queries; inserted into existing pipeline without replacement; significant CTR and transaction number improvements in online A/B.                                                             |

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

**2026 shift:** Agent post-training + structured memory + active tool use — AgenticRec directly optimizes tool-use trajectory via RL; MemRec/MARS structure long-term memory with lifecycle management; CoVeMem makes collaborative memory differentiable and candidate-retrievable. AgentCom further turns cross-user collaboration into routed, failure-evolving communication skills. ReasonRec and industrial systems such as SYF make tool/state use conditional on uncertainty or explicit user control rather than a fixed pipeline.

### Three Clear Trends

1. **Recommendation agents**: The center of gravity has moved from one-shot LLM ranking to persistent state, active evidence acquisition, and explicit user/agent interaction. CoVeMem makes collaborative memory trainable by ranking gradients, while MMEACR lets User and Item Memory Agents reflect over multimodal evidence without discarding fine-grained embeddings. RecThinker adds an Analyze→Plan→Act investigation loop whose SFT+GRPO policy learns which recommendation-specific tools to call. AgentCom, SYF, and the live-catalogue CRS extend the same direction to cross-user skills, persistent profiles, session memory, and production-grounded tool routing.
2. **Search agents**: Search is becoming a trajectory-control problem rather than a query-rewrite module. CAFE jointly evolves a retrieval policy and its in-trajectory critic, while CAS applies conformal uncertainty to both adaptive evidence sets and complete-trajectory GRPO weighting. ReTree repairs contradictions through provenance-aware tree memory and branch rollback; LoongReflect turns reflect/backtrack into learned memory-control actions under global-teacher guidance. The frontier now couples iterative evidence acquisition, uncertainty calibration, reversible memory, reflection, and outcome-aligned trajectory optimization.
3. **Advertising and industrial control**: Agents increasingly operate above low-latency serving as planners, controllers, and experiment-driven policy selectors. AdsWorldEngine extends the stack to conversational ads, jointly improving a dialogue Orchestrator and its retrieval/ranking tools from rewarded rollouts; HOBA and SWAG-Bid provide hierarchical and long-window bidding control. Melo shows the recommendation-side production pattern: a fixed tool graph, live-index verification, and bounded reflective retry can safely serve roughly one million experimental users without requiring a learned controller. Across these systems, online experiments close the feedback loop while gated or constrained execution paths contain operational risk.

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
