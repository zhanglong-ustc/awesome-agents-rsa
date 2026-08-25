# Literature Audit and Refresh Design

## Objective

Audit the existing 2025–2026 collection of agent research in recommendation, search, and advertising, correct unsupported metadata or claims, and add important missing work without weakening the repository's evidence standard.

## Scope

- Include work first published from 1 January 2025 through 25 August 2026.
- Cover recommender systems, search and retrieval, advertising, and production deployments in those domains.
- Treat pre-2025 work as background only.
- Require an agentic mechanism such as planning, memory, tool use, environment interaction, reflection, multi-agent orchestration, or trajectory-level reinforcement learning.
- Exclude plain LLM rerankers or generative recommenders without an agentic loop.

## Evidence Standard

Every retained or newly added entry must be verified against a primary source: the paper page or PDF, an official proceedings page, or an official institutional publication page. Bibliographic fields, agent architecture, experimental setup, and numeric results must be traceable to that source. Claims that cannot be verified will be removed, weakened, or explicitly marked as not reported.

Preprints will not be described as peer-reviewed. Online deployment claims require explicit production, traffic, or A/B-test evidence in the source. The audit will not infer company affiliation, deployment status, or metric improvements from titles or search snippets.

## Repository Design

`data/papers.json` remains the canonical data source. The generated `README.md` and interactive site under `docs/` remain derived outputs. Existing entry identifiers will be preserved where possible so website links remain stable.

For each paper, the data will capture the existing schema's bibliographic metadata, category, agentic tags, concise contribution, resource links, and Chinese and English detail text. The generated README will continue to organize papers by recommendation, search, advertising, and industry deployment, followed by boundaries and trend synthesis.

## Audit and Refresh Workflow

1. Inventory all existing entries and normalize their canonical identifiers, preferably DOI or arXiv ID.
2. Verify each entry's title, authors, institution, publication date, venue, links, architecture, experimental setting, and reported metrics.
3. Record a keep, correct, reclassify, or remove decision for every existing entry.
4. Search primary academic and institutional sources for missing work using multiple topic formulations across the four scope areas.
5. Add only papers that pass the date, domain, agentic-mechanism, and evidence gates.
6. Regenerate README and website outputs from `data/papers.json`.
7. Review per-category trend summaries against the final retained set so they do not overgeneralize beyond the evidence.

## Validation

- Parse and schema-check `data/papers.json`.
- Run `node scripts/generate-readme.mjs` and confirm that a second run produces no diff.
- Check duplicate DOI, arXiv ID, normalized title, URL, and `detailId` values.
- Verify that every main-table entry satisfies the date boundary and agent criterion.
- Check primary links and report any inaccessible or redirected sources.
- Inspect the generated README and website data for consistent counts, categories, links, and bilingual detail content.

## Deliverables

- Corrected and expanded `data/papers.json`.
- Regenerated `README.md` and website content.
- A concise audit record listing corrected, removed, reclassified, and added entries with reasons.
- Validation results recorded in the final task handoff.
- One focused implementation commit, followed by a push to `main` after secure GitHub authentication succeeds.

## Safety and Authentication

The personal access token pasted into chat is considered compromised and will not be used or stored. Repository writes will be pushed only after the user revokes that token and completes GitHub authentication through a secure local or browser-based flow.
