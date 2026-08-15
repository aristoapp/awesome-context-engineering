# LWC

## Snapshot

- Website / docs: https://janyork.github.io/llm-wiki-cli/
- Repo: https://github.com/JanYork/llm-wiki-cli
- Company / maintainer: JanYork / LWC maintainers
- Status: Active public repo; latest release v0.14.7 at review time
- Open source: Yes (Apache-2.0)
- Deployment: Local Rust CLI with canonical SQLite storage and a rebuildable Markdown projection; optional local document-graph and code-graph indexes
- Primary users: Coding-agent users, researchers, and technical operators who want durable local knowledge with source traceability
- Best second-brain role: Agent-operated, source-grounded local Wiki with CLI and read-only MCP access
- Last reviewed: 2026-08-15
- Reviewed evidence: Official repo and documentation at commit `88d72b7b8b98a74ba645e994d8698f0fbb82e419`, v0.14.7 release, and Apache-2.0 license

## One-line Summary

LWC is a local Rust CLI that lets AI agents turn curated sources into a persistent SQLite-backed, Markdown-projected Wiki with citations, lexical retrieval, optional graphs, and integrations for multiple agent hosts.

## Second-Brain Fit

LWC is best understood as an agent-operated local knowledge workspace, not a hosted memory API or consumer notes app. It stores immutable source snapshots separately from agent-maintained Wiki pages, citations, links, provenance, schema, and purpose. SQLite is canonical, while the Markdown tree remains inspectable and rebuildable.

It fits users who want agents to maintain durable project or global knowledge through an explicit ingest and revision workflow. Search is deterministic and lexical, and maintenance is invoked by the user or agent; LWC does not provide automatic app connectors, a built-in LLM, semantic vector recall, or a background consolidation service.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local single-machine deployment. A Rust binary owns a canonical SQLite database and projects Wiki content to Markdown; optional Grafeo or SurrealDB document-graph sidecars and an opt-in CodeGraph index remain local. |
| Context capture | Built-in for curated UTF-8 files through individual source adds, directory imports, or JSON manifests. Sources are immutable snapshots with SHA-256 deduplication and file-status/diff checks. There are no built-in SaaS or OAuth collectors. |
| Knowledge organization | Built-in source records, Wiki pages, citations, wikilinks, explicit provenance, schema and purpose documents, hierarchical spans, and typed graph relations. The agent must analyze sources and maintain the resulting pages. |
| Memory evolution | Built-in but agent-operated. The workflow supports source revision checks, staged changesets, atomic publication, linting, reindexing, Markdown rematerialization, and explicit relation updates. There is no daemon or automatic background consolidation loop. |
| Retrieval / use | FTS-backed document, passage, and sentence search; bounded context and span expansion; page/source filtering; an optional document graph; and an optional code graph. Retrieval is lexical rather than semantic/vector-based. |
| Agent activation / write-back | A unified read-only MCP tool exposes bounded Wiki and optional code context. Portable skills, hooks, and installers support multiple agent hosts; agents write back by invoking the guarded CLI rather than through MCP. |
| Personal / team scope | Built-in project and global scopes for one user on one machine. Combined search can read both scopes, but mutations target one scope. Team workspaces, RBAC, and managed sync are not built in. |
| Feedback / correction | CLI operations support page and source revision, explicit relation retraction, guarded deletion, linting, checkpoints, and changeset rollback. A loopback browser viewer is read-only. |
| Privacy / control | Canonical data and projections are locally owned. The viewer is loopback-only and GET/HEAD-only; CodeGraph is opt-in and telemetry is disabled. Model-provider and external source-tool privacy depend on the surrounding agent workflow. |
| Setup / operations | Medium. Installing one binary is straightforward, but users still initialize scopes, define schema and purpose, curate sources, configure agent integrations, review agent writes, and maintain or optionally enable graph indexes. |

## Strengths

- Keeps source snapshots distinct from synthesized Wiki pages and requires source-backed pages to carry citations.
- Uses local SQLite as the canonical store while keeping knowledge inspectable through a rebuildable Markdown projection and read-only viewer.
- Provides explicit project/global scope, provenance, source freshness checks, guarded deletion, checkpoints, and reversible changesets.
- Offers deterministic lexical retrieval without requiring embeddings or a vector database.
- Integrates with multiple agent hosts through a portable skill, lifecycle hooks, CLI, and a bounded read-only MCP surface.
- Makes document and code graphs optional instead of silently enabling or downloading them.

## Limitations

- Single-machine and single-user; no built-in team workspace, RBAC, hosted sync, or managed governance.
- No built-in SaaS connectors, continuous capture, LLM calls, vector database, or semantic retrieval.
- No daemon or background service; knowledge evolution depends on an agent or user running the documented maintenance workflow.
- The browser viewer is for inspection only; editing and correction happen through the CLI.
- Inputs are UTF-8 text and are bounded to 64 MiB per schema, purpose, source, or page body.
- Optional graph features add setup, local index state, and verification work.

## Best For

- Coding-agent users who want project knowledge to survive sessions in a local, auditable store.
- Researchers and technical operators who value citations, provenance, explicit maintenance, and deterministic retrieval.
- Users who want one local Wiki available to several supported agent hosts without exposing write access through MCP.
- Workflows that need both human-inspectable Markdown and stronger transactional controls than direct file editing provides.

## Not Ideal For

- Users who want automatic email, chat, calendar, or cloud-document connectors.
- Teams that need shared hosted workspaces, permissions, and administrative controls.
- Applications that require a hosted memory API, multi-tenant SDK, or semantic/vector recall.
- Users who want a consumer notes editor or unattended background memory consolidation.

## Tradeoffs

LWC combines local ownership and inspectable Wiki output with citations, transactional updates, and bounded agent access. In return, users accept a CLI-centered workflow, curate the source set, review agent-authored knowledge, and operate any optional indexes themselves. It is a stronger fit for deliberate, auditable local memory than for turnkey capture or team collaboration.

## Official Setup / Evaluation Links

- [LWC documentation](https://janyork.github.io/llm-wiki-cli/)
- [LWC GitHub repo](https://github.com/JanYork/llm-wiki-cli)
- [LWC README](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/README.md)
- [Agent workflow](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/docs/agent-workflow.md)
- [v0.14.7 release](https://github.com/JanYork/llm-wiki-cli/releases/tag/v0.14.7)

## Sources

- [Core design and knowledge model](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/README.md#core-design)
- [Native agent setup and MCP boundary](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/README.md#native-agent-setup)
- [Agent workflow and atomic changes](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/README.md#agent-workflow)
- [Read-only viewer and CodeGraph](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/README.md#read-only-viewer-and-codegraph)
- [Maintenance, limits, and non-goals](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/README.md#maintenance-and-projection)
- [Cargo package metadata](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/Cargo.toml)
- [Apache-2.0 license](https://github.com/JanYork/llm-wiki-cli/blob/88d72b7b8b98a74ba645e994d8698f0fbb82e419/LICENSE)
