# GotSaeng OS

## Snapshot

- Website / docs: https://github.com/wonkwonlee/gotsaeng-os
- Company / maintainer: `wonkwonlee` and GotSaeng OS contributors
- Status: Active public repository; v0.11.0 is published on npm and listed in the Obsidian community plugin registry
- Open source: Yes, MIT License
- Deployment: Local CLI or desktop-only Obsidian plugin; reads a user-selected Markdown vault and writes local Markdown and JSON reports
- Primary users: People with Markdown or Obsidian vaults who want inspectable context packs for human and AI-assisted workflows
- Best second-brain role: Deterministic local context compiler and review workspace for Markdown/Obsidian vaults
- Last reviewed: 2026-08-11
- Reviewed evidence: Official repository at commit `b66551be3bb16f281737e79b3790266b758788e2`, v0.11.0 npm packages and package smoke test, v0.11.0 release assets, official Obsidian registry entry, README, architecture, context schema, workflows, and security audit

## One-line Summary

GotSaeng OS compiles local Markdown vaults into auditable context packs, memory diffs, and review queues for human and AI-assisted workflows without calling an LLM or cloud service.

## Second-Brain Fit

GotSaeng OS is a local workspace and deterministic compiler rather than an agent memory API, semantic retrieval engine, or chatbot. Its CLI and desktop Obsidian plugin scan local Markdown, classify notes, extract explicit facts, decisions, actions, risks, assumptions, questions, and insights, and render 15 Markdown/JSON artifacts with source paths and coverage metadata.

The system adds an inspectable evolution and governance layer over a Markdown vault. A local manifest supports memory diffs between compiles; stale-context, provenance, confidence, contradiction-candidate, engineering-operations, and team-handoff reports create review surfaces. These are deterministic metadata and text-cue heuristics, not semantic fact verification. AI use is explicit and downstream: the CLI or plugin exports files that a user can provide to ChatGPT, Claude, Gemini, or a local model, but GotSaeng OS does not prove that a downstream model loaded or acted on them.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first. The CLI reads a user-selected Markdown directory; the desktop-only Obsidian plugin uses the current local vault. Both write reports to a local output folder. |
| Context capture | Built-in for local Markdown. It scans YAML frontmatter, explicit markers, task lists, common section patterns, and selected Korean/English labels. It has no SaaS connectors, browser capture, media ingestion, or background cloud collector. |
| Knowledge organization | Built-in deterministic classification and extraction into project context, memory snapshot, decision, action, risk, question, provenance, confidence, contradiction-candidate, and machine-readable reports. |
| Memory evolution | Partial and deterministic. `CONTEXT_MANIFEST.json` and `MEMORY_DIFF.md` surface added, changed, newly stale, and resolved context between compiles. There is no semantic consolidation, embedding model, or autonomous dream cycle. |
| Retrieval / use | Generated Markdown/JSON packs, Obsidian Report Hub preview, backlinks, source-note navigation, weekly review output, and local LLM handoff export. No semantic search, vector retrieval, RAG, chat, or memory API. |
| Agent activation / write-back | CLI and Obsidian plugin generate portable files for manual use in AI workflows. No MCP server, agent API/SDK, automatic context injection, or agent write-back path is built in. |
| Personal / team scope | Strong personal and project fit through the selected vault and project name. `TEAM_MEMORY.md` is a handoff report, not a shared workspace; permissions, concurrent editing, sync, and approvals are external. |
| Feedback / correction | Users can inspect reports, follow source-note links in Obsidian, edit source Markdown, and recompile. Provenance, confidence, and contradiction outputs are review queues rather than correctness judgments. |
| Privacy / control | The current runtime has no telemetry, hidden network calls, credential collection, cloud sync, or LLM API calls. Privacy of any later AI upload, model provider, or sync choice is outside GotSaeng OS. |
| Setup / operations | Low-medium. The CLI runs through a published npm package; the Obsidian plugin is available through the community registry. Users still own vault hygiene, backups/sync, source review, and report review. |

## Strengths

- Keeps source notes and generated context in portable Markdown/JSON files.
- Separates deterministic compilation and review heuristics from any downstream model.
- Produces explicit source, coverage, provenance, confidence, stale-context, and contradiction-candidate surfaces.
- Supports both a published CLI and a desktop Obsidian workflow with a source-aware Report Hub.
- Requires no account, cloud service, vector database, model download, API key, or LLM call.
- Documents the limits of its heuristic outputs instead of presenting them as truth verification.

## Limitations

- Input is local Markdown; there are no built-in connectors for email, chat services, web apps, media, or databases.
- No semantic search, embeddings, vector database, RAG, chatbot, or built-in answer generation.
- AI-tool use is a manual file handoff; there is no MCP/API/SDK activation path and no evidence that a downstream AI used the exported context.
- Memory evolution is based on deterministic manifests, diffs, stale detection, and report composition rather than semantic consolidation or autonomous maintenance.
- Provenance and confidence scores use local metadata signals; contradiction candidates use explicit markers and text cues. None verifies whether a claim is true.
- `TEAM_MEMORY.md` supports handoff, but GotSaeng OS has no shared-team permissions, concurrent editing, sync, or approval workflow.
- The Obsidian adapter is desktop-only. Its registry entry currently notes that it has not been manually reviewed by Obsidian staff.

## Best For

- Markdown or Obsidian users who want a deterministic compile step before handing context to an AI tool.
- People who value local ownership, source traceability, portable output, and explicit review queues over automatic retrieval.
- Developers, researchers, and project owners who need decision, action, risk, question, stale-context, and handoff summaries from a vault.
- Users who want no runtime cloud dependency, telemetry, model SDK, or credential handling.

## Not Ideal For

- Users who want automatic SaaS ingestion, background capture, or multimodal collection.
- Agents that need direct MCP/API retrieval, automatic memory injection, or write-back.
- Users who want semantic search, graph/vector retrieval, or an AI chat interface.
- Teams that need built-in RBAC, shared storage, concurrent editing, or managed synchronization.
- Users who want semantic truth checking or autonomous memory consolidation.

## Tradeoffs

GotSaeng OS trades automatic capture, semantic retrieval, and direct agent activation for a small, deterministic, local-only compiler boundary. It gives users inspectable source-linked artifacts and explicit review signals, but users must choose what to send to an AI tool, review heuristic output, maintain source notes, and provide their own sync or collaboration workflow.

## Official Setup / Evaluation Links

- [Repository and quick start](https://github.com/wonkwonlee/gotsaeng-os)
- [npm CLI package](https://www.npmjs.com/package/@gotsaeng/cli)
- [Obsidian community registry entry](https://github.com/obsidianmd/obsidian-releases/blob/master/community-plugins.json)
- [Architecture](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/architecture.md)
- [Context schema](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/context-schema.md)
- [Workflow examples](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/workflows.md)
- [Security and privacy audit](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/security-audit.md)

## Sources

- [GotSaeng OS README](https://github.com/wonkwonlee/gotsaeng-os/blob/main/README.md)
- [MIT License](https://github.com/wonkwonlee/gotsaeng-os/blob/main/LICENSE)
- [v0.11.0 release](https://github.com/wonkwonlee/gotsaeng-os/releases/tag/0.11.0)
- [Context schema](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/context-schema.md)
- [Architecture](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/architecture.md)
- [Security audit](https://github.com/wonkwonlee/gotsaeng-os/blob/main/docs/security-audit.md)
- [Obsidian community plugin registry](https://github.com/obsidianmd/obsidian-releases/blob/master/community-plugins.json)
