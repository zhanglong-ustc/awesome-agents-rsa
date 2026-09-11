# Literature Audit Log

## 2026-09-11

- Scope: daily incremental primary-source screening for work first published from 2025-01-01 through 2026-09-11 across agentic recommendation, user/behavior memory, agentic search, advertising/bidding, and named industrial systems.
- Retrieval: followed the `research-lit` workflow with the available first-party web index and direct official pages. No local PDFs were found in `papers/` or `literature/`; no Zotero or Obsidian source was configured. The official arXiv API was retried through the permitted network route but timed out without a response, so it could not be used to complete a metadata package.
- Candidates: 6 candidate records were mechanically screened after URL/title normalization: RE-Searcher, MR-Search, RTBAgent, and three current Alibaba Cloud product documents. Fully verified and added: 0. Corrected: 0. Removed: 0. The collection remains at 59 entries.
- Decision: no candidate was promoted. The two research papers newly surfaced by this screen lacked a complete first-party affiliation/experimental-metric package within the available primary records; RTBAgent is an already-known 2025 work pending the same full-field recheck. The Alibaba pages are implementation documentation, not authored industrial reports with reproducible evaluation metrics. Search snippets were used only for discovery and supplied no catalog metadata.
- Verification: `node scripts/generate-readme.mjs --check`, JavaScript syntax validation, duplicate URL/detail-ID/title/arXiv/DOI checks for the catalog fields that exist, date-window checks, two consecutive README generations with identical SHA-256, and `git diff --check` passed. A stricter optional audit also found a pre-existing legacy `ReasonRec` record without author/institution/firstPublished fields; this was not altered in this no-addition run and needs a separately sourced correction before it can satisfy the newer full-field standard.

## 2026-09-10

- Scope: incremental primary-source search for 2025-01-01 through 2026-09-10 across agentic recommendation, user modeling, search, advertising, and industrial deployments, with special attention to papers first posted after the previous run and explicit rechecks of the prior backlog.
- Retrieval: the `research-lit` workflow used three read-only fan-out shards for recommendation, search, and advertising/industry, plus direct inspection of official arXiv cs.IR/cs.AI/cs.CL/cs.LG/cs.MA listings, abstract/history pages, full HTML, ACM DOI metadata, and official code links. No local PDFs, Zotero, or Obsidian sources were available; `arxiv_fetch.py` and `verify_papers.py` were unresolved, so first-party paper records and deterministic repository checks supplied the fallback.
- Candidates: 18 unique curated candidates after mechanical arXiv-ID/DOI/normalized-title de-duplication, drawn from 13 recommendation screens, 31 search screens, and an industry scan of 1,300 arXiv OAI records (355 keyword matches). Fully verified and added: 9. Corrected: 0. Removed: 0. The main collection increased from 50 to 59 entries.
- Added recommendation: HyperTrace (`2609.09835`, Findings of EMNLP 2026) for hypothesis-preserving online preference memory; AGAS (`2609.09551`, ICDM 2026) as a multi-agent reflection/memory security stress test; and AtomRec (`2609.04882`) for evolving atomic memory and cross-user evidence paths.
- Added search: RAP (`2609.10092`) for temporally controlled evidence-acquisition bias analysis; Beyond One-Shot Expansion (`2609.07050`, CIKM 2026, DOI `10.1145/3799682.3840072`) for four-round coverage-aware evidence exploration; HAE-GEO (`2609.06027`) for trajectory-level recovery evaluation under hierarchical Web evidence poisoning; and backlog item ITER (`2608.27912`) for interaction-history-aware retriever training from successful agent trajectories.
- Added industry deployment: NetEase AutoLR (`2609.04871`) for multi-agent recommender R&D with persistent experiment state and a human Launch Review gate; and Huawei IGPO (`2609.04813`, EMNLP 2026 Industry Track) for inventory-grounded, replay-validated policy memory in commercial AI search. No unseen advertising-specific paper survived the scope screen.
- Exclusions: nine candidates were not promoted when they lacked a closed-loop agent, used fixed retrieval without meaningful search control, were only weakly tied to recommendation/search/advertising, lacked complete primary-source affiliation metadata, or had not completed the same full-field verification package. Search summaries and secondary pages were used only for discovery, never as metadata or metric evidence.
- Primary sources: official arXiv abstract/history and full-HTML pages for all nine additions; official ACM DOI metadata for the CIKM paper; and linked official GitHub repositories where the first-party paper record exposed code. Venue and deployment claims are limited to explicit paper/arXiv statements.
- Verification: titles, complete author and institution lists, first-publication dates, venues, contributions, agent architectures, experimental settings, original metrics, caveats, arXiv/DOI/official URLs, normalized titles, URLs, and detail IDs were checked. JSON parsing, schema/generator validation, duplicate detection, date-window enforcement, deterministic repeated generation, README/site-data consistency, JavaScript syntax, and diff hygiene were run before commit.

## 2026-09-07

- Scope: incremental primary-source search for 2025-01-01 through 2026-09-07 across agentic recommendation, search, advertising, and major-platform deployments, with priority on work first posted after the previous run at 2026-09-02 01:43 UTC and explicit backlog rechecks.
- Retrieval: `research-lit` read-only fan-out over recommendation, search, and advertising/industry plus a direct arXiv API time-window query, followed by arXiv abstract/history and full-HTML checks. No local PDFs, Zotero, or Obsidian sources were available; `arxiv_fetch.py` and `verify_papers.py` were unresolved, so official arXiv API metadata and first-party full text supplied the deterministic metadata and evidence checks.
- Candidates: 32 unique candidates after mechanical arXiv-ID/DOI/normalized-title de-duplication. Fully verified and added: 11. Corrected: 0. Removed: 0. The main collection increased from 39 to 50 entries.
- Added recommendation: AgentMMRec (`2608.29410`) for multi-agent multimodal knowledge memory and EvoRec (`2606.28368`) for Alibaba's persistent experiment-memory recommender evolution loop.
- Added search: Headroom-Drift Replay (`2609.03941`, COLM 2026), SignBalance (`2609.04063`), SciLENS (`2609.03338`), Marco DeepResearch (`2603.28376`), and Agentic-R (`2601.11888`). Together they cover search-trajectory replay, advantage-estimator bias, local scientific-search tools, verification-centric deep research, and agent–retriever co-training.
- Added advertising: DMRL (`2609.02170`; authors from Shanghai Jiao Tong University and Kuaishou Technology) for document-mediated skill RL with delayed online reward, LangBP (`2608.30343`) for hierarchical joint bidding/pricing, and AIGB-R1 (`2607.17281`) for planner–executor optimization in an interactive auction simulator. DMRL's deployment platform is unnamed in the paper.
- Added industry deployment: Meta CORAL (`2609.02730`, RecSys 2026 OARS Workshop), a persistent-memory and constrained-tool loop evaluated by production A/B tests on two large-scale social recommender surfaces.
- Primary sources: official arXiv API, abstract/history pages, and arXiv HTML full text for every added entry. Venue claims are limited to explicit first-party records; no unnamed deployment is attributed to an author's employer, and simulation-only AIGB-R1 is not described as production evidence.
- Verification: titles, complete author lists, institutions, first publication dates, venue status, agent architecture, experimental settings, original metrics, arXiv/DOI links, normalized titles/URLs/detail IDs, and explicit limitations were checked. Remaining candidates were not promoted when the fit was less direct, complete institution metadata was unavailable, or the work primarily improved a component without completing the same repository-level curation package.

## 2026-09-01

- Scope: incremental primary-source search for 2025-01-01 through 2026-09-01 across agentic recommendation, search, advertising, and major-platform deployments.
- Retrieval: `research-lit` fan-out over recommendation, search, and advertising/industry, followed by direct arXiv abstract/history and full-HTML checks. No local PDFs, Zotero, or Obsidian sources were available; the arXiv helper remained unresolved, so verification used first-party arXiv paper pages.
- Candidates: 26 unique candidates after mechanical arXiv-ID/DOI/normalized-title de-duplication. Fully verified and added: 5. Corrected: 0. Removed: 0.
- Added search: NIS-Agent (`2608.23045`, EMNLP 2026), with context-isolated webpage triage, adaptive query rewriting, and independent premise-to-conclusion validation.
- Added advertising: Astar (`2608.27287`), an Alibaba Lazada advertising-recall evolution system with offline and online evidence; and AB-GRPO (`2608.28199`), a critic-free trajectory-optimization controller evaluated only on public offline bidding environments.
- Added industry deployment: Kuaishou A/B Agent (`2608.04625`) for experiment-driven recommendation-strategy iteration, and Tencent RecSys Factory (`2608.11241`) for bounded-autonomy recommender-lifecycle operations.
- Primary sources: arXiv abstract/history and full HTML for every added entry. NIS-Agent's EMNLP 2026 status was taken from the paper's official arXiv record; deployment, evaluation, and limitation claims for Astar, A/B Agent, and RecSys Factory were taken from the corresponding paper sections rather than search snippets.
- Verification: titles, complete author lists, institutions, first publication dates, venue status, agent architecture, experimental settings, original metrics, and deployment limitations were checked against the paper text. Remaining candidates were not promoted because they were tangential to serving/search/ads scope or had not completed the same full-field curation package in this daily increment.

## 2026-08-30

- Scope: incremental primary-source search for 2025-01-01 through 2026-08-30 across agentic recommendation, search, advertising, and major-platform deployments.
- Retrieval: `research-lit` fan-out over recommendation, search, and advertising/industry, plus direct arXiv paper-history and full-text checks. No local PDFs, Zotero, or Obsidian sources were available; the arXiv helper was unresolved, so structured retrieval degraded to first-party arXiv/ACL/ACM pages.
- Candidates: 35 unique in-scope candidates after mechanical arXiv/DOI/normalized-title de-duplication. Fully verified and added: 7. Corrected: 0. Removed: 0.
- Added recommendation: live-catalogue conversational recommendation (`2608.27006`, DOI `10.1145/3773078.3841297`), MMEACR (`2607.07108`), and RecThinker (`2603.09843`).
- Added search: CAS (`2608.20771`) and LoongReflect (`2608.11967`).
- Added advertising: AdsWorldEngine (`2608.13833`).
- Added industry deployment: Melo (`2607.23718`, DOI `10.1145/3773078.3831935`).
- Primary sources: arXiv abstract/history and full HTML for every added entry; the live-catalogue CRS and Melo RecSys references/DOIs were cross-checked from their first-party paper records. AdsWorldEngine deployment evidence comes from the paper's Microsoft Copilot online-experiment section.
- Verification: titles, complete author lists, institutions, first publication dates, venue status, agent architecture, experimental settings, limitations, and reported metrics were checked against the paper text. Remaining candidates were not promoted because they were lower priority for this daily increment or had not completed the same full-field curation package.

## 2026-08-29

- Scope: incremental primary-source search for 2025-01-01 through 2026-08-29 across agentic recommendation, search, advertising, and major-platform deployments.
- Retrieval: `research-lit` fan-out over recommendation, search, and advertising/industry, plus direct arXiv and ACL Anthology checks. No local PDFs, Zotero, or Obsidian sources were available.
- Candidates: 61 unique candidates after mechanical arXiv/DOI/title de-duplication.
- Added: 7. Corrected: 0. Removed: 0.
- Added recommendation: CoVeMem (`2608.26895`) and AgentCom (`2608.08417`).
- Added search: CAFE (`2608.24794`) and ReTree (`2608.10676`).
- Added advertising: SWAG-Bid (`2607.25233`) and HOBA (`2607.24779`, DOI `10.1145/3770855.3818435`).
- Added industry deployment: Shape Your Feed (`2608.06632`, RecSys 2026 Industrial Track).
- Primary sources: arXiv abstract/history and full HTML/PDF for every added entry; the HOBA ACM DOI and the RecSys acceptance statement were cross-checked from the corresponding first-party paper pages.
- Verification: titles, complete author lists, institutions, first publication dates, venue status, agent architecture, experimental settings, and reported metrics were checked against the paper text. Remaining candidates were not added because they were lower priority for this daily increment or had not yet completed the same full-field verification.
