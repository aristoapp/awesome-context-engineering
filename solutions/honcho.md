# Honcho

## Snapshot

- Website / docs: https://honcho.dev/docs/v3/documentation/introduction/overview
- Company / maintainer: Plastic Labs
- Status: Open-source project with managed and self-hosted deployment paths
- Open source: Yes, AGPL-3.0-licensed repository
- Deployment: Managed Honcho service, local/self-hosted FastAPI server, SDK integration, or MCP server
- Primary users: Developers building stateful agents with persistent memory and user modeling
- Best second-brain role: Stateful agent memory and user-modeling layer
- Last reviewed: 2026-06-10
- Reviewed evidence: Honcho docs, Honcho GitHub repo, Hermes Agent integration guide

## One-line Summary

Honcho is an agent memory library and managed service that stores messages, reasons over peer history, and exposes context, search, representations, conclusions, SDKs, and MCP tools for stateful agents.

## Second-Brain Fit

Honcho fits best when the second brain is part of an agent or application rather than a consumer notes workspace. It is relevant for builders who need agents to maintain state about users, agents, groups, projects, or other entities over time.

For a self-evolving second brain, Honcho covers the collect, organize, evolve, and use stages through message/session storage, peer representations, background reasoning, search, context retrieval, and MCP/API/SDK access. Governance, end-user review UI, connector coverage, and human-facing knowledge workflows depend on the product or agent experience built around it.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Managed service and self-hosted FastAPI server paths are documented; the core repository is AGPL-3.0. |
| Context capture | API/SDK/MCP writes add messages, sessions, and uploaded documents; broader source capture depends on the integrating app or agent. |
| Knowledge organization | Built around workspaces, peers, sessions, messages, conclusions, representations, peer cards, and session context. |
| Memory evolution | Background processing reasons over messages and updates peer representations/conclusions; `schedule_dream` is exposed through MCP. |
| Retrieval / use | Search, get context, peer/session representations, peer cards, conclusions, and chat-style context queries are documented. |
| Agent activation / write-back | MCP, Python/TypeScript SDKs, API, and integrations for Claude Code, OpenCode, OpenClaw, Hermes, and MCP-compatible clients are documented. |
| Personal / team scope | Workspaces isolate applications/environments; peers and sessions can model users, agents, groups, and other entities. |
| Feedback / correction | Developer-facing inspection and conclusion tools exist; a polished end-user correction workflow depends on the integration. |
| Privacy / control | Self-hosting is possible, but operating it requires managing the service, model provider keys, storage, and updates. |
| Setup / operations | Hosted MCP setup is quick for agent clients; self-hosting and production integration require normal backend and memory-design work. |

## Strengths

- Clear primitives for stateful agents: workspaces, peers, sessions, messages, conclusions, and representations.
- MCP support makes it usable from common agent clients.
- Python and TypeScript SDKs support application integration.
- Self-hosting path exists for teams that need more control than the managed service.
- Hermes and OpenClaw integrations make it relevant to agent-memory workflows already tracked in this repo.

## Limitations

- It is agent/application memory infrastructure, not a complete consumer second-brain product.
- End-user UI, source connectors, permission workflows, and review/correction flows depend on the integration.
- Self-hosted use adds service, provider-key, storage, and update operations.
- Vendor claims about benchmark position or social intelligence are not treated as evaluation evidence here.

## Best For

- Developers building agents that need cross-session state.
- Products that need user or agent modeling as part of application memory.
- Agent workflows that want MCP-accessible memory with hosted or self-hosted options.
- Multi-agent systems where users and agents need separate persistent representations.

## Not Ideal For

- Users who want a ready-made second-brain dashboard for notes, sources, and manual knowledge management.
- Teams that need broad SaaS connectors without building app-specific ingestion.
- Workflows where local Markdown inspection is more important than API-managed representations.

## Tradeoffs

Honcho gives builders a flexible state layer for agents, but the user experience is shaped by the application or agent around it. It should be compared with Mem0/OpenMemory, Hindsight, Supermemory, Hyperspell, Zep/Graphiti, and Cognee when the primary need is programmable memory rather than a complete second-brain app.

## Official Setup / Evaluation Links

- Docs: https://honcho.dev/docs/v3/documentation/introduction/overview
- Repository: https://github.com/plastic-labs/honcho
- MCP integration: https://honcho.dev/docs/v3/guides/integrations/mcp
- Hermes integration: https://honcho.dev/docs/v3/guides/integrations/hermes
- API reference: https://honcho.dev/docs/v3/api-reference/introduction

## Sources

- https://honcho.dev/docs/v3/documentation/introduction/overview
- https://github.com/plastic-labs/honcho
- https://honcho.dev/docs/v3/guides/integrations/mcp
- https://honcho.dev/docs/v3/guides/integrations/hermes
