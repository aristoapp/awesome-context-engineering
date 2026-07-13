# Vestige

## Snapshot

- Website / docs: https://github.com/samvallad33/vestige
- Repo: https://github.com/samvallad33/vestige
- Release: https://github.com/samvallad33/vestige/releases/tag/v2.2.1
- Package: https://www.npmjs.com/package/vestige-mcp-server
- Company / maintainer: Sam Valladares (samvallad33), independent
- Status: Open-source Rust MCP server with an embedded dashboard, published to npm and the MCP registry, tagged release v2.2.1
- Open source: Yes, AGPL-3.0-licensed repository (recognized by GitHub)
- Deployment: Local-first. Single prebuilt Rust binary installed through an npm package, run as a local stdio MCP server with a local HTTP/WebSocket dashboard. No cloud, Docker, or API key is required; data stays on the machine.
- Primary users: Developers and agent operators who want local-first, inspectable memory for MCP-compatible coding agents
- Best second-brain role: Local-first agent memory layer with FSRS-6 decay, prediction-error gated writes, active forgetting, and a backward causal-recall path
- Last reviewed: 2026-07-03

## One-line Summary

Vestige is a local-first memory layer for AI agents, shipped as a single Rust binary that runs as an MCP server. It stores memories in local SQLite with a USearch vector index, gates writes with a prediction-error step that merges redundant and supersedes contradictory records, ages memories with FSRS-6 spaced-repetition decay, and exposes a `suppress` tool for reversible active forgetting. Alongside similarity search it ships a backward, entity-linked recall path (`backfill`) intended to surface the upstream cause of a failure rather than its lookalike, plus an embedded 3D dashboard for inspection.

## Second-Brain Fit

Vestige fits best as a developer- or operator-run memory backend for MCP-compatible agents that should run locally and keep their memory inspectable. It is useful when the second brain needs local SQLite ownership, MCP access from coding agents, memory that decays and consolidates over time rather than accumulating flat embeddings, and explicit tools to inspect, correct, suppress, and purge records.

It is closest to Mnemosyne, taOSmd, Mem0/OpenMemory, Hindsight, Honcho, and Cognee in this repo's landscape: more programmable and local-first than hosted memory products, but less ready-made than an end-to-end second-brain app with built-in OAuth connectors, a wiki UI, and team governance. Its main points of difference from those peers are cognitive-science-derived lifecycle behavior (prediction-error gated writes, FSRS-6 decay, consolidation/"dream" maintenance, and reversible top-down suppression) and a backward, entity-based recall path that the maintainer positions as complementary to similarity search rather than another vector ranker.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first. A single prebuilt Rust binary (~23MB) is installed via the `vestige-mcp-server` npm package and run as a local stdio MCP server; storage is local SQLite. No cloud, Docker, or API key is required. First run downloads an embedding model (~130MB) once, after which the maintainer states it runs fully offline. Prebuilt binaries cover macOS (ARM and Intel), Linux x86_64, and Windows x86_64. |
| Context capture | MCP-, CLI-, and agent-driven. `smart_ingest` stores memories and a documented agent-memory protocol lets phrases like "remember this," "I prefer," and "remind me when" trigger saves; `source_sync` indexes external sources (documented for GitHub Issues) into the local index. Capture is agent and developer driven, not a broad OAuth connector layer. |
| Knowledge organization | Local SQLite records with FTS5 full-text search and a USearch HNSW vector index over Nomic Embed v1.5 embeddings. A memory graph with associations and reasoning chains, synaptic tagging, and per-project code memory (`codebase`) provide structure on top of the stored records. |
| Memory evolution | Built-in. Writes pass through prediction-error gating that merges redundant and supersedes contradictory memories; FSRS-6 spaced-repetition decay ages memories so used ones persist and unused ones fade; a `maintain` verb runs consolidation, a "dream" pass that links and synthesizes across memories, and garbage collection; `dedup` detects and merges duplicates. |
| Retrieval / use | `recall` folds similarity search, cross-memory reasoning, and contradiction detection into one call using Reciprocal Rank Fusion. `backfill` adds a separate backward, entity-linked recall path intended to surface a failure's upstream cause. MCP, CLI, and the dashboard can retrieve context; `intention` supports prospective "remind me when X" triggers. |
| Agent activation / write-back | Built-in stdio MCP server (command `vestige-mcp`) plus a CLI. The README documents setup for Claude Code, Codex, Cursor, Windsurf, VS Code (Copilot), Cline, Continue, Zed, Goose, JetBrains, Xcode, OpenCode, and Claude Desktop through a universal MCP config. Agents can read and write memory (create, edit, promote, demote, suppress, purge). |
| Personal / team scope | Partial. Per-project code memory and local scoping separate contexts, but there is no team-permission or shared-workspace product surface; memory is local to the machine. |
| Feedback / correction | Built-in operator tools: `memory` gets, edits, promotes, demotes, and purges records (content plus embeddings); `suppress` applies reversible top-down forgetting; `contradictions` inspection surfaces conflicting memories; supersede is part of the write path. |
| Privacy / control | Local-first: local SQLite storage with optional SQLCipher encryption, no cloud calls after the one-time model download, and export/backup/restore through `maintain`. Embedding behavior depends on the local model. |
| Setup / operations | Medium. Install is one npm command plus an MCP config entry, but production value depends on the agent-memory protocol wiring, memory-scope design, and how the maintenance and suppression tools are used. Intel Mac needs a Homebrew ONNX Runtime path documented in the repo. |

## Strengths

- Ships as a single local Rust binary installed from npm, running as a local stdio MCP server with no cloud, Docker, or API key required; storage is local SQLite with optional SQLCipher encryption.
- MCP server and CLI are documented across many coding-agent clients through one universal config, and agents can write back (create, edit, promote, demote, suppress, purge), not only read.
- Cognitive-science-derived lifecycle behavior is built in: prediction-error gating merges redundant and supersedes contradictory writes, FSRS-6 decay ages memory, and a `maintain` verb runs consolidation, a "dream" synthesis pass, and garbage collection.
- Active forgetting (`suppress`) is a first-class tool: top-down inhibition that the maintainer describes as compounding, cascading to graph neighbors, and reversible within a 24h window, so the memory is inhibited rather than immediately erased.
- A backward, entity-linked recall path (`backfill`) is offered alongside similarity search, aimed at surfacing a failure's upstream cause instead of its closest-looking match.
- Explicit governance surfaces exist for inspection and correction: get/edit/promote/demote, contradiction inspection, purge of content plus embeddings, and export/backup/restore, plus an embedded 3D dashboard for browsing the memory graph.
- Mechanisms are documented against cited papers in a science doc, and the project reports 1,550 passing tests with a clippy `-D warnings` clean build.

## Limitations

- It is a local agent memory backend, not a full consumer second-brain application; broad OAuth app connectors, a hosted option, and team permissions are not the product surface.
- Memory is local to one machine; there is no team-permission or shared-workspace layer, and portability across machines is user-operated (export/backup/restore).
- The maintainer's causal-recall benchmark is a self-run, maintainer-published measurement and should not be treated as independent third-party evaluation without reproduction (see Benchmarks note below).
- AGPL-3.0 licensing may not fit every downstream use; evaluate license fit before embedding it in a product.
- Retrieval, consolidation, and suppression quality depend on the local embedding model, configuration, memory-scope design, and how the agent-memory protocol is wired.

## Best For

- Coding-agent users who want MCP-accessible local memory for Claude Code, Codex, Cursor, Windsurf, VS Code, or similar clients without operating a hosted service.
- Developers who want memory that decays, consolidates, dedupes, and supersedes over time rather than a flat, ever-growing embedding store.
- Users who want explicit inspection and correction surfaces, including reversible active forgetting and content-plus-embedding purge, over an opaque memory store.
- Users who prefer local SQLite ownership (optionally SQLCipher-encrypted) over a managed memory platform.

## Not Ideal For

- Users who want a hosted dashboard, built-in OAuth connectors, and the lowest possible setup burden.
- Teams that need workspace permissions, admin controls, and a governance UI out of the box.
- Source-grounded research workflows where a bounded notebook or wiki is enough.
- Downstream products where AGPL-3.0 licensing is a blocker.

## Tradeoffs

Vestige gives strong local control, cognitive-science-derived lifecycle behavior, and explicit inspection, correction, and forgetting surfaces, but it shifts model operation, memory-scope design, and agent-protocol wiring to the user, and it is single-machine and local-only rather than a hosted or team product. Compare it with Mnemosyne, taOSmd, Mem0/OpenMemory, Hindsight, Honcho, and Cognee when the primary need is local or programmable agent memory rather than a complete hosted second-brain product, and weight it higher when built-in decay, consolidation, contradiction handling, reversible forgetting, or a backward causal-recall path matter most, and when AGPL-3.0 licensing is acceptable.

## Benchmarks

The maintainer publishes a causal-recall benchmark ("CauseBench") in which pure vector retrievers scored 0% recall@1 on a causal-gap task while Vestige scored about 60%. The maintainer is explicit that two separate claims are in play and should not be conflated: a 2026 Google DeepMind result (arXiv:2508.21038, ICLR 2026) is cited as a theorem that single-vector retrieval cannot bridge such gaps, while the 0%-vs-60% figure is the maintainer's own local measurement. Treat the 0%-vs-60% number as a maintainer-published, self-run measurement rather than independent third-party validation, and reproduce it before relying on it. The backward-recall mechanism itself (`backfill`, "Retroactive Salience Backfill") is documented as a port of Zaki/Cai et al. 2024, *Nature* 637:145–155.

## Official Setup / Evaluation Links

- Repository: https://github.com/samvallad33/vestige
- Release v2.2.1: https://github.com/samvallad33/vestige/releases/tag/v2.2.1
- npm package: https://www.npmjs.com/package/vestige-mcp-server
- Science doc: https://github.com/samvallad33/vestige/blob/main/docs/SCIENCE.md
- Agent memory protocol: https://github.com/samvallad33/vestige/blob/main/docs/AGENT-MEMORY-PROTOCOL.md
- Claude Code setup: https://github.com/samvallad33/vestige/blob/main/docs/CLAUDE-SETUP.md
- Configuration: https://github.com/samvallad33/vestige/blob/main/docs/CONFIGURATION.md

## Sources

- https://github.com/samvallad33/vestige
- https://github.com/samvallad33/vestige/blob/main/README.md
- https://github.com/samvallad33/vestige/releases/tag/v2.2.1
- https://github.com/samvallad33/vestige/blob/main/docs/SCIENCE.md
- https://www.npmjs.com/package/vestige-mcp-server
