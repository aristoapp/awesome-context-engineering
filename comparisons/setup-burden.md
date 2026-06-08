# Setup Burden

## Low Burden

| Solution | What you do | What you do not operate |
|---|---|---|
| [Membase](../solutions/membase.md) | Create an account, use dashboard chat, optionally connect an AI tool/plugin, import chat history, Gmail/Google Calendar/Slack, Notion, or Wiki material. | Storage, indexing, hosted retrieval, background organization, MCP server hosting, and connector plumbing; Notion sync, Drive, and GitHub are coming soon unless verified. |
| [OpenHuman](../solutions/openhuman.md) | Install desktop app, onboard, connect selected apps, choose managed or custom providers. | Local memory plumbing and default integration orchestration. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | Turn memory settings on or off and manage saved memories. | External connectors, MCP, vector DBs, or custom collectors. |
| [NotebookLM](../solutions/notebooklm.md) | Create a notebook and add sources. | Indexing infrastructure or custom retrieval code. |

## Medium Burden

| Solution | What you operate | Main risk |
|---|---|---|
| [Supermemory](../solutions/supermemory.md) | MCP/API auth, optional project scoping, connectors, API usage. | Connector status, project boundaries, and source deletion semantics. |
| [Hyperspell](../solutions/hyperspell.md) | App/API keys, user tokens, Hyperspell Connect, source selection, metadata/collection design, MCP or SDK integration. | Private beta availability and app-owned governance/review UI. |
| [Honcho](../solutions/honcho.md) | Hosted MCP/API key or self-hosted FastAPI server, SDK/MCP integration, peer/session design, provider keys for self-hosting. | Agent memory quality depends on integration design; self-hosting adds backend operations. |
| [Mnemosyne](../solutions/mnemosyne.md) | Python package, local SQLite data path, MCP/SDK/Hermes plugin configuration, embedding settings, memory banks, and consolidation cadence. | Easy to start, but retrieval quality and write-back safety depend on agent integration and memory-scope design. |
| [taOSmd](../solutions/taosmd.md) | Source install of the Python package, a local embedding model, a local LLM (Ollama or RKLLM), the data directory, and optional MCP or HTTP serve configuration. | Easy to start from source, but there is no PyPI package yet, and retrieval and extraction quality depend on the local models and configuration. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | API keys, SDK integration, hosted or self-hosted stack. | Memory scope design, governance, and retrieval tuning. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | App integration, user/session/group model, graph ingestion, graph backend, LLM/embedding provider. | Requires product engineering rather than end-user setup. |
| [Cognee](../solutions/cognee.md) | Python package/SDK setup, optional MCP client config, optional Docker or API/Cloud mode, graph processing. | Separate standalone instances vs shared API mode can fragment memory. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | Hermes install/config, `WIKI_PATH`, source curation, Markdown review, lint/maintenance cadence. | Easy to start, but quality depends on agent discipline and user review. |
| [Khoj](../solutions/khoj.md) | Cloud or self-host install, source configuration, indexing. | Self-hosting and source freshness need active management. |

## High Burden

| Solution | What you operate | Main risk |
|---|---|---|
| [GBrain](../solutions/gbrain.md) | Local CLI/init, brain repo, import/sync/embed, dream/autopilot, stdio/HTTP MCP, recipes or collectors; company brain adds source/OAuth/database design. | Official personal setup targets about 30 minutes, but broad active-context coverage is still operated by the user. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Vault hygiene, plugins or bridges, local model/API choices, sync and backups. | Strong ownership, but AI behavior depends on the bridge you build. |

## Practical Rule

Start with the lowest setup burden that satisfies your privacy and portability needs. Move to a local/self-hosted stack only when you have a real reason to own storage, indexing, or graph construction.
