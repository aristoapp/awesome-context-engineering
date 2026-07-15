# marm-memory

## Snapshot

- Website / docs: https://github.com/Lyellr88/marm-memory
- Repo: https://github.com/Lyellr88/marm-memory
- Package: https://pypi.org/project/marm-mcp-server/
- Company / maintainer: Ryan Lyell / marm-memory
- Status: Apache-2.0-licensed local-first MCP memory server with HTTP and STDIO transports; the public repository documents 14 MCP tools and an embedded legacy dashboard.
- Open source: Yes, Apache-2.0-licensed repository
- Deployment: Local Python package or Docker image. Memory is stored in local SQLite under `~/.marm/`; HTTP normally listens on loopback and STDIO runs as a local process.
- Primary users: Developers and agent operators who want a shared local memory layer for MCP-compatible coding and AI clients
- Best second-brain role: Local-first agent memory layer with hybrid recall, session logs, optional knowledge/code graphs, and staged memory maintenance
- Last reviewed: 2026-07-15

## One-line Summary

marm-memory is a local-first MCP memory server that stores agent session logs and semantic memories in SQLite, exposes hybrid recall over HTTP and STDIO, and adds optional concept and code-graph workflows without requiring a hosted service.

## Second-Brain Fit

marm-memory fits best as an agent memory layer rather than a local workspace or end-to-end second-brain app. Developers connect MCP-capable agents to one local server, have them write structured session entries, and retrieve durable context through hybrid FTS5 and embedding-based recall. The same installation can also expose notebooks, staged compaction, a concept graph, and a codebase graph.

It covers organization, maintenance, retrieval, and local inspection well once agents are connected, but capture is agent-driven rather than connector-driven: it does not ship OAuth ingestion for email, calendars, Slack, or document suites. The embedded dashboard is a legacy SQLite administration UI; the separate MARM Console is still in active development and is not the basis for this profile.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first Python package or Docker image. The core memory database is local SQLite in `~/.marm/marm_memory.db`; the concept graph uses a separate local SQLite database. No managed hosted MARM service is documented. |
| Context capture | MCP-driven structured logging and memory capture. Agents write session entries with `marm_log_entry`; those entries also become semantic memories. Capture depends on agent workflow and does not include built-in OAuth connectors or automatic imports from third-party apps. |
| Knowledge organization | Session logs, summaries, notebooks, project/platform metadata, FTS5-backed memories, and optional extracted concept entities/relationships. The optional code graph indexes local repositories separately from the memory store. |
| Memory evolution | Optional write-time exact/semantic consolidation and an agent-assisted staged compaction workflow. The server detects and stages candidates; an agent reviews, summarizes, applies, or discards them. |
| Retrieval / use | `marm_smart_recall` combines exact FTS5 retrieval with bounded semantic reranking and supports session, project, and platform scoping. Optional concept and code-graph tools provide graph-oriented retrieval after explicit builds/indexing. |
| Agent activation / write-back | Built-in HTTP and STDIO MCP transports expose the same 14 tools to MCP-compatible clients. Agents can log, recall, manage notebooks, request summaries, and perform compaction workflow actions. A general-purpose SDK is not the primary public surface. |
| Personal / team scope | Strong personal and project fit through local databases, session names, and project/platform metadata. A shared HTTP server can coordinate multiple agents against one database, but team permissions, hosted sync, and multi-tenant governance are not built-in. |
| Feedback / correction | Partial. The legacy dashboard provides direct local SQLite inspection/management, while MCP exposes log/session/notebook deletion and reviewable compaction actions. General semantic-memory mutation APIs and the replacement Console are still in development. |
| Privacy / control | Local SQLite ownership and loopback-by-default HTTP. Network-exposed HTTP requires `MARM_API_KEY`; Docker HTTP is documented with bearer auth. First use of optional embeddings or the bundled graph engine can require dependency/model download. |
| Setup / operations | Medium. A local install needs Python plus an MCP client configuration; Docker is available. Semantic recall uses fastembed, concept extraction needs the optional spaCy extra and model, and shared HTTP use requires one process per SQLite database. |

## Strengths

- One local MCP installation supports both HTTP and STDIO with the same 14-tool surface.
- Session logs dual-write into semantic memory, so operational notes can be retrieved through hybrid recall rather than remaining separate history.
- Local SQLite, FTS5, bounded semantic reranking, and project/platform scoping provide an inspectable local memory path without a required cloud account.
- Optional concept extraction and local codebase indexing extend the memory layer without making core memory tools depend on graph availability.
- Consolidation and compaction are explicit, reviewable maintenance paths rather than opaque destructive background rewriting.
- Loopback-by-default HTTP, local Docker support, and a legacy dashboard provide practical local operation and inspection surfaces.

## Limitations

- It is an agent memory server, not a ready-made second-brain app with OAuth connectors, broad automatic collection, or a polished end-user workspace.
- Useful capture depends on agents following the logging/memory workflow; there is no built-in automatic import from chat platforms, email, calendars, or documents.
- Team permissions, hosted synchronization, multi-tenant governance, and cross-machine collaboration are not built-in product surfaces.
- Semantic recall, concept extraction, and code graph features have separate optional/runtime dependencies and can degrade when unavailable; core logging and memory remain available.
- The standalone MARM Console is in active development, so it should not be evaluated as a shipped governance UI yet.

## Best For

- Coding-agent users who want local persistent context shared across Claude Code, Codex, Cursor, Gemini, Qwen, VS Code, or other MCP-compatible clients.
- Developers who want a local SQLite-backed memory layer with HTTP or STDIO transport rather than a hosted memory platform.
- Teams or individuals who can operate one local HTTP process and want session/project scoping, hybrid recall, and reviewable memory maintenance.
- Workflows that benefit from optionally linking agent memory to an extracted concept graph or local codebase graph.

## Not Ideal For

- Users who want automatic capture from third-party SaaS tools without designing agent or connector workflows.
- Non-technical users who need a finished desktop or hosted second-brain application rather than MCP setup and local runtime operation.
- Organizations that require built-in multi-tenant access control, hosted sync, SSO, or a mature team governance product.
- Workflows that need guaranteed semantic/graph capabilities but cannot install or operate their optional dependencies.

## Tradeoffs

marm-memory prioritizes local ownership, MCP interoperability, and explicit agent-controlled maintenance over connector breadth and turnkey user experience. It is a strong fit when agents are the primary writers and readers of a local memory store, but users take responsibility for MCP configuration, capture discipline, local dependency setup, and any team-level sharing or permissions model. Compare it with Mnemosyne, taOSmd, Vestige, Hindsight, Honcho, and Mem0/OpenMemory when deciding between a local MCP memory layer, a hosted/self-hosted developer primitive, or a broader agent-memory platform.

## Official Setup / Evaluation Links

- Repository and README: https://github.com/Lyellr88/marm-memory
- MCP protocol overview: https://github.com/Lyellr88/marm-memory/blob/MARM-main/docs/PROTOCOL.md
- FAQ: https://github.com/Lyellr88/marm-memory/blob/MARM-main/docs/FAQ.md
- PyPI package: https://pypi.org/project/marm-mcp-server/
- Docker image: https://hub.docker.com/r/lyellr88/marm-mcp-server

## Sources

- https://github.com/Lyellr88/marm-memory
- https://github.com/Lyellr88/marm-memory/blob/MARM-main/README.md
- https://github.com/Lyellr88/marm-memory/blob/MARM-main/AGENTS.md
- https://github.com/Lyellr88/marm-memory/blob/MARM-main/docs/FAQ.md
- https://github.com/Lyellr88/marm-memory/blob/MARM-main/marm-mcp-server/pyproject.toml
