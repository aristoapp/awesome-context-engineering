# Local vs Cloud

| Solution | Local / self-hosted | Hosted / cloud | Best reason to choose it | Main tradeoff |
|---|---|---|---|---|
| [Membase](../solutions/membase.md) | Not the primary model | Yes | Fast end-to-end second brain without running the stack | Less local infrastructure control. |
| [OpenHuman](../solutions/openhuman.md) | Yes, local memory/runtime state and Markdown vault | Yes, managed services for sign-in, model routing, search proxying, OAuth/integrations | Productized local-first personal AI | Local-first does not mean fully offline by default. |
| [GBrain](../solutions/gbrain.md) | Yes, local PGLite and self-hosted Postgres/Supabase paths | HTTP MCP can be deployed remotely | Maximum control over second-brain operations | PGLite fits local personal use; shared/team deployments add Postgres/Supabase, OAuth, sync, embeddings, collectors, and maintenance. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | Yes, local/server Hermes runtime plus Markdown wiki directory | Optional only through chosen hosting, sync, or model providers | Inspectable agent-maintained wiki | No managed connector/governance layer; user owns wiki hygiene and runtime configuration. |
| [Supermemory](../solutions/supermemory.md) | API/self-hosting details depend on product path | Yes | Hosted memory API with connectors | Hosted convenience with platform boundaries. |
| [Hyperspell](../solutions/hyperspell.md) | Public SDK/MCP/plugin repos, but core memory platform is hosted | Yes | Hosted connector, context graph, and retrieval layer for agents | Private beta availability and less local infrastructure control. |
| [Honcho](../solutions/honcho.md) | Yes, self-hosted FastAPI server | Yes, managed service and hosted MCP | Stateful agent memory with hosted or owned deployment paths | Self-hosting adds service, provider-key, storage, and update operations. |
| [Mnemosyne](../solutions/mnemosyne.md) | Yes, local SQLite database through package, MCP, SDK, or Hermes plugin | Not the primary model | Local-first agent memory for MCP and Hermes workflows | You operate embeddings, memory scope, consolidation, and agent integration behavior. |
| [taOSmd](../solutions/taosmd.md) | Yes, local-first and offline; local SQLite, ONNX embeddings, and a local LLM (Ollama or RKLLM on RK3588) | Not a hosted product; an optional remote client can target your own taosmd serve instance | Offline, local-first agent memory on modest or single-board hardware with a zero-loss archive | You run and operate the local LLM and embedding model yourself. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | Yes through OSS/self-hosted setup | Yes through Mem0 Platform | Developer memory layer with hosted or owned stack | Requires memory scope and governance design. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | Graphiti is open source; Zep is managed | Yes | Temporal graph memory for apps | Product engineering and backend/provider choices required. |
| [Cognee](../solutions/cognee.md) | Yes, SDK/local setup and optional Docker MCP | Yes, API/Cloud mode/shared backend | Knowledge graph memory SDK with MCP/plugins | Mode choice affects sharing and isolation. |
| [Khoj](../solutions/khoj.md) | Yes | Yes | Personal AI over files with privacy option | Self-hosting still requires source and model setup. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | Yes | Optional sync/services | Human-owned local notes | AI memory requires plugins or custom bridges. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | No | Yes | Native ChatGPT personalization | Platform-bound and not portable. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Claude Code has local terminal/IDE/desktop surfaces; project knowledge is platform-hosted | Yes | Claude-native project context and developer-agent workflows | Platform-scoped unless external MCP memory is added. |
| [NotebookLM](../solutions/notebooklm.md) | No | Yes | Source-grounded research notebook | Static imported sources and platform-bound workflow. |

## Guidance

Local-first systems are better for ownership, auditability, custom schema work, and long-lived personal archives. Hosted systems are better when setup speed, OAuth connectors, background organization, and ready-to-use retrieval matter more than operating the storage layer.
