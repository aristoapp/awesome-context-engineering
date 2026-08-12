# GotSaeng OS

## Snapshot

- Website / docs: https://github.com/wonkwonlee/gotsaeng-os
- Company / maintainer: `wonkwonlee` and GotSaeng OS contributors
- Status: Active public repository; v0.12.0 is published on npm (`@gotsaeng/core`, `@gotsaeng/cli`, `@gotsaeng/mcp`) and listed in the Obsidian community plugin registry
- Open source: Yes, MIT License
- Deployment: Local CLI, local stdio MCP server, or desktop-only Obsidian plugin; reads a user-selected Markdown vault and writes local Markdown and JSON reports
- Primary users: People with Markdown or Obsidian vaults who want inspectable context packs for human and AI-assisted workflows, and AI coding agents that need structured tool access to that same compile pipeline
- Best second-brain role: Deterministic local context compiler and review workspace for Markdown/Obsidian vaults, with a stdio MCP surface for agent activation
- Last reviewed: 2026-08-12
- Reviewed evidence: Official repository README, `docs/mcp.md`, `docs/architecture.md`, `docs/context-schema.md`, `docs/workflows.md`, and `docs/security-audit.md`; the npm registry entry for `@gotsaeng/mcp` (dist-tags `latest: 0.12.0`, confirming a real, non-placeholder publish); v0.12.0 release notes

## One-line Summary

GotSaeng OS compiles local Markdown vaults into auditable context packs, memory diffs, and review queues for human and AI-assisted workflows, and exposes that same pipeline to MCP clients as read/compile-only tools, all without calling an LLM or cloud service.

## Second-Brain Fit

GotSaeng OS is a local workspace and deterministic compiler rather than an agent memory API, semantic retrieval engine, or chatbot. Its CLI, MCP server, and desktop Obsidian plugin all wrap the same core: scan local Markdown, classify notes, extract explicit facts, decisions, actions, risks, assumptions, questions, and insights, and render 15 Markdown/JSON artifacts with source paths and coverage metadata.

The system adds an inspectable evolution and governance layer over a Markdown vault. A local manifest supports memory diffs between compiles; stale-context, provenance, confidence, contradiction-candidate, engineering-operations, and team-handoff reports create review surfaces. These are deterministic metadata and text-cue heuristics, not semantic fact verification. The `@gotsaeng/mcp` stdio server (`validate_vault`, `compile_context_pack`, `list_context_artifacts`, `read_context_artifact`, `prepare_ai_handoff`) lets an MCP client — Claude Code, Codex, Cursor — call this same pipeline directly as structured tools instead of a human manually copying exported files into a chat window, but the vault/output roots are fixed at server launch and every tool is read/compile-only: nothing in GotSaeng OS writes back to the source vault, and it does not prove that the calling agent actually used what it read.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first. The CLI and MCP server read a user-selected Markdown directory, launched via CLI flags; the desktop-only Obsidian plugin uses the current local vault. All three write reports to a local output folder. |
| Context capture | Built-in for local Markdown. It scans YAML frontmatter, explicit markers, task lists, common section patterns, and selected Korean/English labels. It has no SaaS connectors, browser capture, media ingestion, or background cloud collector. |
| Knowledge organization | Built-in deterministic classification and extraction into project context, memory snapshot, decision, action, risk, question, provenance, confidence, contradiction-candidate, and machine-readable reports. |
| Memory evolution | Partial and deterministic. `CONTEXT_MANIFEST.json` and `MEMORY_DIFF.md` surface added, changed, newly stale, and resolved context between compiles. There is no semantic consolidation, embedding model, or autonomous dream cycle. |
| Retrieval / use | Generated Markdown/JSON packs, Obsidian Report Hub preview, backlinks, source-note navigation, weekly review output, and an LLM handoff export that an MCP client can request and read directly via `prepare_ai_handoff` / `read_context_artifact`. No semantic search, vector retrieval, RAG, or chat interface. |
| Agent activation / write-back | Built-in stdio MCP server (5 tools, JSON-RPC over stdin/stdout, no network listener) plus the CLI and Obsidian plugin. All three are read/compile-only — no tool, command, or plugin action writes back to the source vault; every write lands in the configured local output directory. |
| Personal / team scope | Strong personal and project fit through the selected vault and project name. `TEAM_MEMORY.md` is a handoff report, not a shared workspace; permissions, concurrent editing, sync, and approvals are external. |
| Feedback / correction | Users can inspect reports, follow source-note links in Obsidian, edit source Markdown, and recompile. Provenance, confidence, and contradiction outputs are review queues rather than correctness judgments. |
| Privacy / control | The current runtime has no telemetry, hidden network calls, credential collection, cloud sync, or LLM API calls. The MCP server treats vault content as untrusted data, not instructions, and caps read sizes. Privacy of any later AI upload, model provider, or sync choice is outside GotSaeng OS. |
| Setup / operations | Low. The CLI and MCP server both run through `npx` from published npm packages (`@gotsaeng/cli`, `@gotsaeng/mcp`); the Obsidian plugin is available through the community registry. Users still own vault hygiene, backups/sync, source review, and report review. |

## Strengths

- Keeps source notes and generated context in portable Markdown/JSON files.
- Separates deterministic compilation and review heuristics from any downstream model.
- Produces explicit source, coverage, provenance, confidence, stale-context, and contradiction-candidate surfaces.
- Ships the same deterministic pipeline through three surfaces — CLI, MCP, and a desktop Obsidian workflow with a source-aware Report Hub — so the same compiler backs whichever entry point a user or agent reaches for.
- The MCP server is explicit about its own boundary: fixed vault/output roots set once at launch, no arbitrary path arguments, an allowlist chokepoint for every artifact read/write, size-capped reads, and tool descriptions that mark vault content as untrusted data rather than instructions.
- Requires no account, cloud service, vector database, model download, API key, or LLM call.
- Documents the limits of its heuristic outputs instead of presenting them as truth verification.

## Limitations

- Input is local Markdown; there are no built-in connectors for email, chat services, web apps, media, or databases.
- No semantic search, embeddings, vector database, RAG, chatbot, or built-in answer generation.
- MCP tools are read/compile-only: an agent can call `compile_context_pack` and read artifacts back, but nothing writes to the source vault, and GotSaeng OS has no way to confirm a calling agent actually used what it read.
- Memory evolution is based on deterministic manifests, diffs, stale detection, and report composition rather than semantic consolidation or autonomous maintenance.
- Provenance and confidence scores use local metadata signals; contradiction candidates use explicit markers and text cues. None verifies whether a claim is true.
- `TEAM_MEMORY.md` supports handoff, but GotSaeng OS has no shared-team permissions, concurrent editing, sync, or approval workflow.
- The Obsidian adapter is desktop-only. Its registry entry currently notes that it has not been manually reviewed by Obsidian staff.

## Best For

- Markdown or Obsidian users who want a deterministic compile step before handing context to an AI tool, whether by hand or through an MCP client.
- Coding-agent workflows (Claude Code, Codex, Cursor) that want a vault's context pack as a structured tool call instead of a manual file copy.
- People who value local ownership, source traceability, portable output, and explicit review queues over automatic retrieval.
- Developers, researchers, and project owners who need decision, action, risk, question, stale-context, and handoff summaries from a vault.
- Users who want no runtime cloud dependency, telemetry, model SDK, or credential handling.

## Not Ideal For

- Users who want automatic SaaS ingestion, background capture, or multimodal collection.
- Agents that need write-back into the source vault, automatic memory injection, or a semantic recall API — MCP access here is read/compile-only.
- Users who want semantic search, graph/vector retrieval, or an AI chat interface.
- Teams that need built-in RBAC, shared storage, concurrent editing, or managed synchronization.
- Users who want semantic truth checking or autonomous memory consolidation.

## Tradeoffs

GotSaeng OS trades automatic capture, semantic retrieval, and vault write-back for a small, deterministic, local-only compiler boundary that is now reachable through MCP as well as a CLI and an Obsidian plugin. It gives users and agents inspectable, source-linked artifacts and explicit review signals through a structured tool surface, but the surface is read/compile-only, users still choose what an agent or a human sees, review heuristic output, maintain source notes, and provide their own sync or collaboration workflow.

## Official Setup / Evaluation Links

- [Repository and quick start](https://github.com/wonkwonlee/gotsaeng-os)
- [npm CLI package](https://www.npmjs.com/package/@gotsaeng/cli)
- [npm MCP package](https://www.npmjs.com/package/@gotsaeng/mcp)
- [MCP server guide](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/mcp.md)
- [Obsidian community registry entry](https://github.com/obsidianmd/obsidian-releases/blob/master/community-plugins.json)
- [Architecture](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/architecture.md)
- [Context schema](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/context-schema.md)
- [Workflow examples](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/workflows.md)
- [Security and privacy audit](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/security-audit.md)

## Sources

- [GotSaeng OS README](https://github.com/wonkwonlee/gotsaeng-os/blob/main/README.md)
- [MIT License](https://github.com/wonkwonlee/gotsaeng-os/blob/main/LICENSE)
- [MCP server guide](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/mcp.md)
- [npm registry: @gotsaeng/mcp](https://www.npmjs.com/package/@gotsaeng/mcp)
- [Context schema](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/context-schema.md)
- [Architecture](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/architecture.md)
- [Security audit](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/security-audit.md)
- [Obsidian community plugin registry](https://github.com/obsidianmd/obsidian-releases/blob/master/community-plugins.json)
