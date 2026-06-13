# Hermes Agent + LLM Wiki

## Snapshot

- Website / docs: https://hermes-agent.nousresearch.com/
- Repo / skill: https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki
- Company / maintainer: Nous Research / Hermes Agent maintainers
- Status: Active public repo with bundled `llm-wiki` skill
- Open source: Yes
- Deployment: Hermes runs on the user's server or machine; the wiki is a local Markdown directory
- Primary users: Local-first AI operators, researchers, and agent users who want an inspectable Markdown second brain
- Best second-brain role: Agent-operated local Markdown wiki
- Last reviewed: 2026-06-10
- Reviewed evidence: Hermes Agent website, official `hermes-agent` repo, bundled `skills/research/llm-wiki/SKILL.md`

## One-line Summary

Hermes Agent + LLM Wiki uses a bundled Hermes skill to build, query, lint, and maintain an interlinked Markdown knowledge base from raw sources.

## Second-Brain Fit

Hermes Agent + LLM Wiki is best understood as a local, agent-operated wiki pattern rather than a managed second-brain product. It gives an agent explicit instructions for turning files, URLs, papers, transcripts, and pasted text into raw sources, entity pages, concept pages, comparisons, query pages, an index, and an append-only log.

This is a good fit when the user wants knowledge to compound in readable Markdown and is comfortable letting an agent maintain structure. It is not a connector-heavy hosted product, a team governance layer, or a generic memory API.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local/server-owned. Hermes runs on user-controlled infrastructure, and the wiki defaults to `~/wiki` or the configured `WIKI_PATH`. |
| Context capture | Built-in through the skill workflow for URLs, PDFs, pasted text, files, articles, papers, transcripts, and assets. It is not a broad OAuth connector layer by itself. |
| Knowledge organization | Built-in Markdown wiki structure with `SCHEMA.md`, `index.md`, `log.md`, raw source folders, entity pages, concept pages, comparison pages, query pages, YAML frontmatter, tags, wikilinks, confidence fields, and contradiction markers. |
| Memory evolution | Partial / agent-operated. The skill defines ingest, re-ingest, query filing, lint, drift checks, page splitting, archive, and log rotation behaviors, but quality depends on the agent following the skill and the user running or scheduling maintenance. |
| Retrieval / use | Built-in through wiki orientation, file search, relevant page reads, synthesis from compiled pages, and optional filing of valuable answers back into `queries/` or `comparisons/`. It is not a vector database or graph RAG engine by default. |
| Agent activation / write-back | Built-in inside Hermes as a bundled skill. The agent can create and update Markdown wiki files when invoked. |
| Personal / team scope | Partial. Multiple wiki directories, schemas, or vaults can separate projects, but team permissions and governance are filesystem/sync/process concerns, not built-in product controls. |
| Feedback / correction | Built-in in Markdown terms: users can inspect and edit pages, run lint, mark low-confidence or contested pages, and trace claims back to raw source files. |
| Privacy / control | Strong local file control for the wiki. Actual model, browser, web extraction, and sync privacy depend on the Hermes deployment and provider configuration. |
| Setup / operations | Medium. Hermes has a quick install path, but users still choose where the wiki lives, curate sources, review agent writes, and maintain the wiki over time. |

## Strengths

- Bundled directly in the official Hermes Agent repo.
- Produces inspectable Markdown instead of opaque memory records.
- Separates raw sources from curated wiki pages.
- Encourages schema, index, log, provenance, confidence, and contradiction hygiene.
- Works naturally with Obsidian-compatible wikilinks and local file review.
- Fits the "compile once, reuse often" LLM Wiki pattern.

## Limitations

- Not a managed connector product; source capture is agent/file/workflow driven.
- Not a hosted dashboard with account, project, team, retention, or export controls.
- Not a vector database, graph database, or automatic cross-app memory layer by default.
- Quality depends on the agent following the skill instructions and the user's review discipline.
- Team use requires external filesystem, git, sync, vault, or permission design.
- OpenClaw-style LLM Wiki workflows may exist through installable/community skills, but OpenClaw core was not verified to include LLM Wiki as a built-in feature.

## Best For

- Users who want a local, readable, long-lived Markdown second brain.
- Researchers who want sources compiled into entity, concept, and comparison pages.
- Hermes users who want a built-in skill for LLM Wiki workflows.
- People who prefer inspectable files over hosted memory infrastructure.

## Not Ideal For

- Users who want one-click app connectors and hosted background organization.
- Teams that need built-in workspace permissions and admin controls.
- Builders who need a memory API/SDK for an application backend.
- Users who do not want to review or maintain agent-written Markdown.

## Tradeoffs

Hermes Agent + LLM Wiki gives strong local inspectability and a clear knowledge-compilation workflow, but it shifts more responsibility to the user and agent loop. It is a powerful DIY/local-first path, not a low-burden end-to-end second-brain product.

## Official Setup / Evaluation Links

- [Hermes Agent website](https://hermes-agent.nousresearch.com/)
- [Hermes Agent GitHub repo](https://github.com/NousResearch/hermes-agent)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hermes LLM Wiki SKILL.md](https://raw.githubusercontent.com/NousResearch/hermes-agent/main/skills/research/llm-wiki/SKILL.md)

## Sources

- [Hermes Agent website](https://hermes-agent.nousresearch.com/)
- [Hermes Agent GitHub repo](https://github.com/NousResearch/hermes-agent)
- [Hermes LLM Wiki skill directory](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hermes LLM Wiki SKILL.md](https://raw.githubusercontent.com/NousResearch/hermes-agent/main/skills/research/llm-wiki/SKILL.md)
- [Karpathy LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
