# Pad

## Snapshot

- Website / repo: https://getpad.dev · https://github.com/PerpetualSoftware/pad
- Company / maintainer: Perpetual Software LLC
- Status: Active public repo
- Open source: Yes (Apache 2.0)
- Deployment: Self-hosted single Go binary with local SQLite (default); Docker image on GHCR; Unraid Community Apps; Postgres + Redis for multi-instance; hosted cloud at app.getpad.dev
- Primary users: Developers and the AI agents working alongside them
- Best second-brain role: Structured, agent-operated project and knowledge workspace; a substrate for building custom typed agent-memory systems
- Last reviewed: 2026-06-09
- Reviewed evidence: Public repo `README.md`, `CLAUDE.md`, the embedded `/pad` agent skill (`skills/pad/SKILL.md`), the MCP catalog (`internal/mcp/`, tool surface v0.4), and hands-on inspection of the running CLI + MCP server (`pad bootstrap`, `pad_*` tool catalog)

## One-line Summary

Pad is a single-binary, local-first project workspace for developers and AI agents — typed collections of structured items with rich content, wiki-links, full-text search, and first-class agent activation through a native skill, MCP, REST API, and CLI.

## Second-Brain Fit

Pad is best understood as a structured, agent-operated workspace and a substrate on which a custom typed memory system can be built — not a freeform PKM canvas, a vector database, or a no-code notes app. Its distinctive angle for this audience is *context engineering for agents*: always-on **conventions** (project rules agents must follow), invokable **playbooks** (multi-step procedures, including agent-authored maintenance loops), and a one-round-trip **bootstrap** context blob give an agent durable, queryable working context before it acts. Retrieval is structured and full-text rather than semantic, and "memory evolution" is driven by status lifecycle, an audit trail, version history, and whatever maintenance playbooks you author — there is no built-in embedding, dedupe, or automatic consolidation.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted single Go binary (pure-Go SQLite, no CGO) with all data in `~/.pad/pad.db`; Docker image on GHCR; one-click install via the Unraid Community Apps plugin; Postgres + Redis for multi-instance. A hosted cloud option runs at app.getpad.dev for users who prefer managed operation. Local mode runs offline with no telemetry and no accounts required. |
| Context capture | Structured items created via CLI, web UI, REST API, or MCP, each with typed fields plus optional rich Markdown content and file/image attachments. Wiki-links (`[[Title]]`), parent/child hierarchy, and GitHub PR linking. No external SaaS collectors (Gmail, Slack, calendars) — capture is through Pad's own surfaces. |
| Knowledge organization | Typed **collections** with JSON-schema fields (select, text, date, number, url, relation, checkbox); parent/child nesting with progress tracking; explicit dependencies (blocks / blocked-by); cross-item `[[wiki-links]]`; and agent-facing **conventions** (trigger-based rules) and **playbooks** (invokable procedures) as first-class structured items. Reference numbers (`TASK-5`, `BUG-12`) are assigned automatically. |
| Memory evolution | Status lifecycle with mandatory change comments, a full attributed activity feed (agent vs. human), per-item version diff history, and appendable implementation notes / decision-log entries. Maintenance is agent-driven: playbooks can implement revalidation/forgetting loops over custom fields (e.g. a `last_validated_at` staleness sweep). No built-in embedding, deduplication, or automatic consolidation. |
| Retrieval / use | SQLite FTS5 full-text search, structured field filters, computed dashboards, and project intelligence (`next`, `standup`, `changelog`). Agents load a one-round-trip `bootstrap` blob (workspace + collections + always-on conventions + roles + playbook metadata + dashboard) and read workspace state by URL through MCP resources. Retrieval is keyword/structured, not vector/semantic. |
| Agent activation / write-back | Full read + write across a native `/pad` skill for Claude Code, Cursor, Windsurf, Codex, GitHub Copilot, Amazon Q, and JetBrains Junie; a local stdio MCP server (hand-curated v0.4 catalog — eight resource×action tools plus `pad_set_workspace`); a REST API; and a first-class CLI. A remote MCP path (OAuth / PAT bearer) serves hosted users at mcp.getpad.dev. |
| Personal / team scope | Workspace-per-project model linked by a `.pad.toml` file. Multi-user with role-based access control (`owner`, `editor`, `viewer`), email/CLI-code invitations, and real-time collaborative editing (Yjs/Tiptap). |
| Feedback / correction | Web UI board/list/table editing with a rich text editor; a fully attributed activity feed that records what each agent changed; per-item version diff; threaded comments; and workspace export/import. |
| Privacy / control | Local-first by default: data lives in a SQLite file you own, runs offline, no telemetry, no required accounts. Workspace export/import for portability. The managed cloud option places data on the provider's infrastructure for users who opt into it. |
| Setup / operations | Low for self-host: `brew install` then `pad init` (one command: configure, auth, workspace, agent skill) with a single binary and no external dependencies. Docker is a one-line `docker run`, and the Unraid Community Apps entry is a one-click install. Multi-instance (Postgres + Redis) adds operational ownership. The hosted cloud at app.getpad.dev removes local setup entirely. |

## Strengths

- Genuine local-first ownership: a single binary, pure-Go SQLite, your data in one file, offline-capable, no telemetry.
- Unusually broad, write-capable agent activation surface — native skill across 7+ tools, local stdio MCP, remote MCP, REST API, and CLI — so the same workspace is reachable however an agent connects.
- Conventions + playbooks + the bootstrap blob make this a strong *context-engineering* layer: durable, queryable rules and procedures an agent reads before acting.
- Flexible typed collections let you model domain-specific memory (custom fields like confidence, last-validated, generalization) rather than a fixed notes schema.
- Every agent action is attributed in the activity feed, with version diff history — clear provenance and correction surfaces.
- Smooth setup: `pad init` plus an auto-activated onboarding playbook that adapts the workspace to the project.
- Apache 2.0, active repo, and a documented MCP stability contract (versioned tool surface) external agents can pin against.

## Limitations

- No built-in semantic/vector retrieval — search is keyword (FTS5) and structured filters only.
- No automatic memory consolidation, dedupe, or embedding; "evolution" is status/audit/version plus whatever maintenance playbooks you author.
- Building a real agent-memory system on Pad is a deliberate, design-it-yourself exercise on the primitives (typed collections + playbooks), not a turnkey feature.
- Project-management heritage: the model is item/task-centric, not a freeform PKM or document canvas.
- No external SaaS collectors (email, chat, calendar) — context enters through Pad's own CLI/UI/API/MCP/PR-link surfaces.

## Best For

- Developers and AI agents that want a self-hosted, owned workspace for project and working context.
- Teams that want agents to operate through MCP/CLI/API with attributed, inspectable changes.
- Builders who want to design a custom, typed agent-memory or context-engineering layer on flexible primitives.

## Not Ideal For

- Users who want semantic recall or automatic memory consolidation out of the box.
- People who want a freeform notes/PKM canvas rather than structured, typed items.
- Workflows that need one-click connectors pulling from external SaaS sources.

## Tradeoffs

Pad gives you strong local ownership and an exceptionally broad, write-capable agent surface, but it deliberately ships primitives rather than an opinionated memory engine: there is no semantic retrieval or automatic consolidation, so the depth of any "second brain" you build depends on the collection schemas and maintenance playbooks you design. It is a better fit when you want to own and shape an agent-operated workspace than when you want a turnkey, self-evolving memory product.

## Official Setup / Evaluation Links

- [Pad README](https://github.com/PerpetualSoftware/pad/blob/main/README.md)
- [Pad documentation](https://getpad.dev/docs)
- [Pad local MCP guide](https://getpad.dev/mcp/local)
- [Pad remote MCP guide](https://www.getpad.dev/mcp/remote)
- [Pad hosted cloud](https://app.getpad.dev)
- [Pad CLAUDE.md (agent/development guide)](https://github.com/PerpetualSoftware/pad/blob/main/CLAUDE.md)

## Sources

- [Pad GitHub repo](https://github.com/PerpetualSoftware/pad)
- [Pad README](https://github.com/PerpetualSoftware/pad/blob/main/README.md)
- [Pad website](https://getpad.dev)
- [Pad documentation](https://getpad.dev/docs)
- [Pad local MCP guide](https://getpad.dev/mcp/local)
- [Pad remote MCP guide](https://www.getpad.dev/mcp/remote)
</content>
</invoke>
