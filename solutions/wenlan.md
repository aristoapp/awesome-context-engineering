# Wenlan

## Snapshot

- Website / docs: https://wenlan.app
- Repository: https://github.com/7xuanlu/wenlan
- Company / maintainer: 7xuanlu and contributors
- Status: Active public repository with published releases
- Open source: Yes, Apache-2.0
- Deployment: Local Rust daemon with desktop, CLI, MCP, plugin, and localhost HTTP clients
- Primary users: Researchers, writers, consultants, product teams, and software teams using AI across continuing work
- Best second-brain role: Source-backed local AI knowledge base with maintained Markdown pages
- Last reviewed: 2026-08-09
- Reviewed evidence: Official repository README, setup docs, CLI/MCP docs, plugin docs, and license

## One-line Summary

Wenlan turns documents, notes, and past AI conversations into source-cited Markdown pages that agents can retrieve through MCP and keep current as the underlying sources change.

## Second-Brain Fit

Wenlan is a local workspace for work that continues across projects and AI sessions. It keeps three kinds of material distinct: traceable Sources, atomic Memories for decisions and corrections, and maintained Pages that synthesize current knowledge with citations and `[[wikilinks]]`.

Its closest second-brain role is a source-backed implementation of the Karpathy LLM-wiki pattern. Registered files can resync, machine-maintained Pages can refresh from their current support, and changes to human-edited Pages become reviewable revisions instead of silent overwrites. A local daemon is the source of truth; the desktop app, CLI, MCP connectors, Claude Code and Codex plugins, and localhost HTTP API use the same store.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first. A Rust daemon owns the local store; Pages and session notes are Markdown under `~/.wenlan/`, while Memories and graph data use local libSQL. The desktop app is currently a macOS Apple Silicon preview; headless runtime paths also cover Linux glibc and Windows x64, with platform-specific caveats. |
| Context capture | Built-in import for ChatGPT and Claude export ZIPs plus registered `.md`, `.txt`, text-extractable `.pdf`, folders, and read-only Obsidian vault sources. A localhost HTTP API accepts prepared text and Memories from custom capture workflows; broad SaaS OAuth collection is not built in. |
| Knowledge organization | Built-in Source Pages, atomic typed Memories, maintained Knowledge Pages, evidence links, citations, `[[wikilinks]]`, Spaces, entities, directed relations, and Page/Memory history. |
| Memory evolution | Built-in but operational. Registered files sync, explicit supersession preserves corrections, optional model-backed enrichment links entities, and eligible machine Pages can refresh. Citation-poor refresh drafts are rejected; human-edited Pages receive proposed revisions for review. |
| Retrieval / use | Hybrid local retrieval combines FTS5, BGE embeddings, and reciprocal-rank fusion. Optional Page, episodic, fact, graph, and reranking channels can add context; CLI, MCP, and plugins expose search, recall, brief, and page workflows. |
| Agent activation / write-back | Built-in through local MCP connectors, CLI, Claude Code and Codex plugins, and localhost HTTP. Agents can capture atomic knowledge, recall relevant context, read Pages, distill updates, and write handoffs. |
| Personal / team scope | Spaces provide explicit retrieval scope for work, personal, client, or repository knowledge. Local files and scopes support individual and project workflows; built-in team RBAC and hosted concurrent editing are not the primary product shape. |
| Feedback / correction | Built-in desktop inspection, citations, source links, revisions, curation queues, explicit supersession, and read-only `doctor`/`lint` health checks. Users can edit Markdown directly; human-owned Page changes are review-gated on refresh. |
| Privacy / control | Base retrieval and storage remain local. Enrichment and synthesis can use an on-device model, a local endpoint, or a configured cloud provider, so model-provider privacy depends on user configuration. |
| Setup / operations | Medium. `npx -y wenlan setup` installs and verifies the supported headless runtime on macOS Apple Silicon, while Linux and Windows use documented platform paths. Users still own model choice, backups, source selection, review, and any sync outside Wenlan. |

## Strengths

- Keeps source material, learned decisions, and synthesized Pages traceable instead of flattening them into one opaque memory store.
- Citation-gated refresh and reviewable human edits make source-backed maintenance a product behavior rather than only an agent prompt.
- Uses ordinary Markdown Pages with local history, source links, and Obsidian-compatible workflows.
- Exposes the same local knowledge system to multiple AI clients through MCP and maintained Claude Code/Codex plugins.
- Supports an explicit daily loop: brief, capture, recall, handoff, distill, lint, and curate.
- Apache-2.0 repository with CLI, daemon, MCP, desktop integration, plugins, and documented platform boundaries.

## Limitations

- The desktop app is currently a macOS Apple Silicon preview; other platforms use headless/runtime paths, and macOS Intel lacks a supported complete-runtime install.
- Broad hosted-app connectors, automatic email/calendar capture, team RBAC, and a managed cloud workspace are not built in.
- Source extraction is limited to supported text-bearing formats; image-only scanned PDFs need OCR before Wenlan can ingest their text.
- Local ownership does not make configured cloud-model calls or external sync providers private.
- Model-backed enrichment and synthesis quality depends on the selected model and review discipline.
- It is a user-operated local knowledge system, not a low-effort hosted memory API for embedding inside another product.

## Best For

- People who want an inspectable AI knowledge base built from documents, notes, and past AI work.
- Coding-agent users who need the same source-backed Pages and project context in Claude Code, Codex, Cursor, or other MCP clients.
- Teams or individuals who value citations, revision review, correction history, and local Markdown ownership.
- LLM-wiki users who want a maintained implementation rather than only a folder convention or prompt.

## Not Ideal For

- Users who want one-click SaaS connectors and a fully hosted second brain.
- Teams that require built-in cloud collaboration, RBAC, and administrative controls.
- Application developers who only need a hosted memory API or SDK substrate.
- Users who do not want to operate local software, choose a model path, or review generated knowledge.

## Tradeoffs

Wenlan trades hosted convenience and broad connector coverage for local ownership, source traceability, and explicit maintenance controls. It provides more built-in runtime, retrieval, citation, and review behavior than a bare Markdown wiki, but users still operate the daemon, source set, model configuration, backups, and review cadence.

## Official Setup / Evaluation Links

- [Website and documentation](https://wenlan.app)
- [Repository and quick start](https://github.com/7xuanlu/wenlan)
- [AI-assisted setup](https://github.com/7xuanlu/wenlan/blob/main/docs/setup-with-ai.md)
- [CLI and MCP guide](https://github.com/7xuanlu/wenlan/blob/main/crates/wenlan-cli/README.md)
- [Codex plugin](https://github.com/7xuanlu/wenlan/blob/main/plugin-codex/README.md)
- [Source-backed Pages](https://wenlan.app/docs/source-backed-pages)
- [Review and trust](https://wenlan.app/docs/review-and-trust)

## Sources

- [Wenlan README](https://github.com/7xuanlu/wenlan/blob/main/README.md)
- [Technical foundations](https://github.com/7xuanlu/wenlan/blob/main/docs/technical-foundations.md)
- [AI-assisted setup](https://github.com/7xuanlu/wenlan/blob/main/docs/setup-with-ai.md)
- [CLI and MCP README](https://github.com/7xuanlu/wenlan/blob/main/crates/wenlan-cli/README.md)
- [Codex plugin README](https://github.com/7xuanlu/wenlan/blob/main/plugin-codex/README.md)
- [Apache-2.0 License](https://github.com/7xuanlu/wenlan/blob/main/LICENSE)
