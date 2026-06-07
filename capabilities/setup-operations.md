# Setup / Operations

## What This Capability Means

Setup and operations cover first install, authentication, source sync, indexing, retries, background jobs, verification, upgrades, and ongoing maintenance.

## Evaluation Questions

- How long until first useful memory?
- Which runtime and accounts are required?
- Who operates storage, embeddings, MCP servers, and collectors?
- How do users know the setup is actually working?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Account + dashboard chat; optional AI tool/plugin connection. | Fastest path, hosted tradeoff. |
| OpenHuman | Built-in + Integration | Native desktop install, onboarding, app connections, provider choices. | Early beta; connector setup can expand scope. |
| GBrain | Built-in + Custom collector | CLI/init, brain repo, import/sync/embed jobs, dream/autopilot, stdio/HTTP MCP; company brain adds source/OAuth/database design. | Official agent install targets about 30 minutes for personal use, but production source coverage remains operations-heavy. |
| Hermes Agent + LLM Wiki | Built-in skill | Install/configure Hermes, optionally set `WIKI_PATH`, curate sources, review Markdown output, and run lint or maintenance passes. | Hermes has a quick install path, but wiki quality is operational and review-dependent. |
| Supermemory | Built-in + Integration | MCP/API and connectors. | Connector health and project scoping matter. |
| Hyperspell | Built-in + Integration | Dashboard/API key, SDK/API or MCP setup, app user IDs or user tokens, Hyperspell Connect, source selection, and metadata/scope design. | Official under-5-minute claim is plausible for a demo; production setup depends on beta access, app integration, and governance choices. |
| Honcho | Integration | Hosted MCP/API key or self-hosted FastAPI server, SDK/MCP integration, peer/session design, and provider keys for self-hosting. | Hosted agent setup is quick; production integration and self-hosting add backend operations. |
| Mem0/OpenMemory | Integration | Hosted MCP/API or self-hosted stack. | Memory design is application work. |
| Zep/Graphiti | API | App integration, graph ingestion, graph backend, and LLM/embedding provider setup. | Builder-focused; official quickstarts exist, but hands-on time varies with backend choices. |
| Cognee | Built-in | Python package/SDK setup, optional MCP config, optional Docker or API/Cloud mode. | Docker is not required; choose mode carefully. |
| Khoj | Built-in | Cloud or self-host plus sources. | Source freshness needs verification. |
| Obsidian/Logseq + AI bridge | Integration | Notes app plus plugin/import/MCP bridge. | Strong ownership, more setup choices. |
| ChatGPT Memory | Built-in | Enable or manage ChatGPT memory settings. | Instant, but platform-bound. |
| Claude Projects/Claude Code | Built-in + Integration | Create a project, add knowledge, configure sharing/connectors, or use Claude Code. | Connector and team behavior depends on plan. |
| NotebookLM | Built-in | Create a notebook and add supported sources. | Source refresh behavior depends on source type. |

## Sources

- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Hermes Agent website](https://hermes-agent.nousresearch.com/)
- [Hyperspell quickstart](https://docs.hyperspell.com/core/quickstart)
- [Hyperspell manual integration](https://docs.hyperspell.com/core/integration)
- [Supermemory MCP setup](https://supermemory.ai/docs/supermemory-mcp/setup)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [Cognee installation](https://docs.cognee.ai/getting-started/installation)
