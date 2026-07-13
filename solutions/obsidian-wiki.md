# obsidian-wiki

## Snapshot

- Website / docs: https://github.com/Ar9av/obsidian-wiki
- Package: https://pypi.org/project/obsidian-wiki/
- Company / maintainer: Ar9av and contributors
- Status: Active public repository and published Python package
- Open source: Yes, MIT License
- Deployment: Local Markdown/Obsidian vault operated through installed agent skills and optional local CLI utilities
- Primary users: People who use one or more coding agents and want an inspectable, portable second brain
- Best second-brain role: Agent-agnostic, local knowledge-compilation framework for Obsidian
- Last reviewed: 2026-07-11
- Reviewed evidence: Official repository README, package metadata, bundled skills, and license

## One-line Summary

obsidian-wiki installs a shared set of Markdown skills that let multiple coding agents ingest sources, merge durable knowledge into an Obsidian vault, query it, and maintain its structure over time.

## Second-Brain Fit

obsidian-wiki is a local workspace and operating pattern rather than a hosted memory service. Its skills instruct supported agents to compile documents, URLs, conversation histories, project context, and rough notes into interlinked Markdown pages with required frontmatter, source provenance, an index, an activity log, and a manifest that tracks ingested sources.

It is distinct from a generic Obsidian AI bridge because the repository supplies the knowledge lifecycle: setup, ingest, agent-history import, delta-aware project updates, query, capture, lint, deduplication, cross-linking, synthesis, dashboards, export, rebuild, and daily maintenance. The same vault can be used from several agent clients, but the model and execution quality still depend on whichever agent runs a skill.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first. The source of truth is a user-selected Obsidian-compatible Markdown directory; configuration points agents and the CLI to that vault. |
| Context capture | Built-in skill workflows for files, folders, URLs, PDFs, images, raw text, chat exports, and histories from Claude Code, Codex, Hermes, OpenClaw, Copilot CLI, and Pi. Broad SaaS OAuth collection is not built in. |
| Knowledge organization | Built-in categories, frontmatter, summaries, source tracking, wikilinks, index/log/hot-cache files, controlled tags, project pages, and merge-in-place rules intended to avoid duplicate pages. |
| Memory evolution | Built-in but agent-operated. Manifests support delta ingest; maintenance skills cover update, lint, deduplication, cross-linking, synthesis, rebuild/restore, tag normalization, daily freshness checks, and hot-cache refresh. These jobs run when invoked or scheduled, not as a continuously managed service. |
| Retrieval / use | Built-in wiki query skill plus local CLI graph query. The query workflow ranks metadata and graph candidates before selectively reading pages and returns answers with links to the underlying wiki pages. |
| Agent activation / write-back | Built-in through portable skills and filesystem access for Claude Code, Codex, Cursor, Windsurf, Gemini CLI, Hermes, OpenClaw, Pi, Copilot CLI, and other agents that read instruction files. No dedicated MCP server or hosted API is required. |
| Personal / team scope | Strong personal and project fit; named vault profiles and per-invocation routing separate contexts. Team sharing, concurrent edits, permissions, and approval workflows depend on external filesystem, Git, or Obsidian Sync choices. |
| Feedback / correction | Strong file-level inspection: users can edit Markdown directly in Obsidian, review provenance, lint broken links/metadata, find duplicates, archive/rebuild, and restore snapshots. Agent writes are not gated by a built-in approval UI. |
| Privacy / control | Vault files remain local and exportable Markdown. Privacy of model prompts, web reads, embeddings, sync, and agent history depends on the selected agent, model provider, optional QMD configuration, and storage/sync setup. |
| Setup / operations | Medium. `pip install obsidian-wiki` plus `obsidian-wiki setup --vault ...` installs shared skills and configuration; users still operate backups, sync, source review, agent runs, and maintenance cadence. |

## Strengths

- One readable Markdown vault can be used across many coding-agent clients.
- Covers the lifecycle beyond retrieval: ingest, merge, provenance, delta tracking, querying, linting, deduplication, synthesis, export, and rebuild.
- Keeps the compiled knowledge and its graph inspectable in Obsidian.
- Dedicated history-ingest skills can distill prior sessions from several coding agents.
- Named vault profiles and inline routing support multiple personal or work brains without changing the default vault.
- MIT-licensed, dependency-light core package with portable skill instructions.

## Limitations

- The agent executing a skill is responsible for extraction, merging, and file edits; results vary with model capability and instruction following.
- No built-in SaaS connector platform, continuously running ingestion service, or dedicated memory API/MCP server.
- Automated evolution is maintenance-command or scheduler driven rather than an always-on managed consolidation loop.
- Team permissions, conflict resolution, review gates, and shared-vault sync are external concerns.
- Local vault ownership does not make calls to a chosen model provider, browser, sync provider, or optional search index private or offline.
- The framework is optimized for durable compiled knowledge, not low-latency per-turn episodic memory.

## Best For

- Multi-agent users who want one portable knowledge base across coding tools.
- People who want agent-maintained knowledge to remain editable and auditable in Obsidian.
- Developers and researchers who regularly distill documents, project decisions, and agent conversations.
- Users willing to run or schedule explicit maintenance instead of adopting a hosted memory service.

## Not Ideal For

- Users who want one-click OAuth connectors and background capture from business apps.
- Teams that require built-in RBAC, approvals, concurrent editing, and admin governance.
- Application developers looking for a memory API or SDK backend.
- Users who want invisible, automatic episodic memory with no file or vault maintenance.

## Tradeoffs

obsidian-wiki trades hosted automation and product-managed governance for portability, inspectability, and cross-agent reuse. It provides more lifecycle discipline than a bare Obsidian vault, but users still own the agent choice, maintenance cadence, sync, backups, and review of generated knowledge.

## Official Setup / Evaluation Links

- [Repository and quick start](https://github.com/Ar9av/obsidian-wiki)
- [PyPI package](https://pypi.org/project/obsidian-wiki/)
- [Wiki setup skill](https://github.com/Ar9av/obsidian-wiki/blob/main/.skills/wiki-setup/SKILL.md)
- [Wiki ingest skill](https://github.com/Ar9av/obsidian-wiki/blob/main/.skills/wiki-ingest/SKILL.md)
- [Wiki query skill](https://github.com/Ar9av/obsidian-wiki/blob/main/.skills/wiki-query/SKILL.md)
- [Wiki lint skill](https://github.com/Ar9av/obsidian-wiki/blob/main/.skills/wiki-lint/SKILL.md)

## Sources

- [obsidian-wiki README](https://github.com/Ar9av/obsidian-wiki/blob/main/README.md)
- [Package metadata](https://github.com/Ar9av/obsidian-wiki/blob/main/pyproject.toml)
- [Bundled skills](https://github.com/Ar9av/obsidian-wiki/tree/main/.skills)
- [MIT License](https://github.com/Ar9av/obsidian-wiki/blob/main/LICENSE)
