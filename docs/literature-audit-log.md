# Literature Audit Log

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
