# BundleDex

## Snapshot

- Website / docs: https://bundledex.net
- Company / maintainer: McClawdDigital
- Status: Live
- Open source: Yes (awesome-okf list at https://github.com/McClawdDigital/awesome-okf)
- Deployment: Cloudflare Workers / GitHub Pages
- Primary users: AI agents, developers, and knowledge workers who want to discover and use OKF knowledge bundles
- Best second-brain role: Knowledge discovery and bundle registry (Organize stage)
- Last reviewed: 2026-07-05

## One-line Summary

BundleDex is a curated directory of 240+ Open Knowledge Format (OKF) bundles that serves as a registry for agents and humans to discover, evaluate, and consume structured knowledge.

## Second-Brain Fit

BundleDex fits the **Organize** stage of the second-brain lifecycle. OKF bundles are pre-structured, portable knowledge packages — concepts with YAML frontmatter, cross-links, and version control — that can be ingested by AI agents or humans. BundleDex makes them discoverable through search, categorization, and a machine-readable JSON API at `/api/bundles.json`.

In a second-brain workflow, OKF bundles serve as structured building blocks that agents can reference, compose, and evolve. Rather than reinventing knowledge from scratch, an agent can pull an existing OKF bundle (e.g., a programming framework's concepts, a domain model, or a skill definition) and combine it with local memory.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Fully hosted at bundledex.net; ownable by anyone who forks the awesome-okf list. |
| Context capture | Not a capture tool. Consumes OKF bundles discovered via the directory. |
| Knowledge organization | Curated taxonomy of 240+ bundles across 6 categories (Example Datasets, Content & Publishing, Tooling & SDKs, Reference & Specifications, AI Agent Skills, Development & Tooling). |
| Memory evolution | Indirect. Bundles can be versioned in Git; BundleDex is a discovery layer, not an evolution engine. |
| Retrieval / use | Web UI search + agent-friendly JSON API at https://bundledex.net/api/bundles.json. |
| Agent activation / write-back | JSON API returns all bundles for agent ingestion. Write-back via /api/submit endpoint (KV-backed). |
| Personal / team scope | Public registry. Personal usage by discovering bundles; team usage by curating shared bundle sets. |
| Feedback / correction | Submit page for adding bundles; GitHub issues on awesome-okf for corrections. |
| Privacy / control | All data public. No private bundles. |
| Setup / operations | Zero setup for consumers. The awesome-okf repo is easy to fork and customize. |

## Strengths

- **Largest OKF bundle index** — 240+ unique bundles, deduplicated and categorized.
- **Agent-native API** — `/api/bundles.json` returns all metadata in one fetch; no auth needed.
- **Curation** — Deduplicated, categorized, quality-scored. Saves hours of manual searching.
- **Vendor-neutral** — Not tied to any agent framework, MCP server, or platform.
- **Free** — No cost to browse or use the API.

## Limitations

- **Discovery-only** — Does not provide memory storage, evolution loops, or reasoning.
- **OKF-only** — Only indexes OKF-format bundles, not arbitrary knowledge sources.
- **No semantic search yet** — Currently keyword/tag based.
- **Public only** — No private bundle hosting or team-scoped registries.

## Best For

- AI agents that need to discover OKF bundles at startup or during workflow execution.
- Developers building agent systems that consume structured knowledge.
- Anyone curious about what OKF bundles exist and which are most popular.
- Second-brain systems that want to seed initial knowledge from curated bundles (Organize stage).

## Not Ideal For

- Continuous memory evolution and consolidation (use dedicated memory layers like Membase, GBrain, or Honcho).
- Capturing scattered context from chats, docs, and apps (Collect stage — use Membase, OpenHuman, or Supermemory).
- Governing, inspecting, or correcting personal memory (Govern stage).
- Semantic search over personal documents.

## Tradeoffs

BundleDex optimizes for **knowledge discovery and curation** — it's the place you go when you need pre-built knowledge packages for your agent or second brain. The tradeoff is that it's purely a registry, not a memory system: it doesn't store user-specific context, evolve memory over time, or provide retrieval augmentation. Think of it as the library catalog, not the librarian.

## Official Setup / Evaluation Links

- [BundleDex](https://bundledex.net)
- [BundleDex API](https://bundledex.net/api/bundles.json)
- [Awesome OKF (GitHub)](https://github.com/McClawdDigital/awesome-okf)
- [Submit a bundle](https://bundledex.net/submit)

## Sources

- https://bundledex.net
- https://github.com/McClawdDigital/awesome-okf