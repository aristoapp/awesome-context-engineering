# Privacy / Control

## What This Capability Means

Privacy, portability, and control cover where memory is stored, whether users can inspect and correct it, how deletion/export works, and whether the system can be self-hosted, exported, or audited.

## Evaluation Questions

- Can users view, edit, delete, and export memories?
- Is memory local, hosted, or self-hosted?
- Are sources and provenance visible?
- Can users control what agents can write?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Partial | Hosted controls, dashboard browsing, project assignment, and deletion flows. | Memory manual create/edit is not available from the Memories tab yet; verify export, retention, and deletion requirements. |
| OpenHuman | Partial | Local Memory Tree, Markdown vault, and runtime state with managed services for default experience. | Local-first does not mean fully offline by default. |
| GBrain | Built-in | Local/self-hosted files and database. | User owns operations and backups. |
| Hermes Agent + LLM Wiki | Built-in for wiki files | Wiki content is local Markdown that users can inspect, edit, back up, move, or delete. | Privacy still depends on Hermes runtime, model provider, browser/web extraction, and any sync service used. |
| Supermemory | Partial | Hosted app, API, connector management. | Connector deletion semantics need review. |
| Hyperspell | Partial | User tokens, source connection controls, metadata filters, folder skip/manual/sync policies, manual review flows, and homepage deletion claims. | Hosted by default; export, retention, deletion, and plan-specific governance should be verified. |
| Honcho | Built-in for self-hosting | Managed service or self-hosted FastAPI server; workspaces and peers provide scoping primitives. | Self-hosting gives more control but adds service, storage, provider-key, and update operations. |
| Mnemosyne | Built-in for local storage | Local SQLite database, export/import commands, memory update/delete/invalidate tools, and configurable data directory. | Embedding, LLM, sync, and agent behavior still depend on configured providers and workflow choices. |
| taOSmd | Built-in for local storage | Offline local SQLite stores, a configurable data directory, correction and supersede tools, and an append-only archive that retains the raw turn; secrets are redacted on the A2A bus. | Embedding and LLM behavior depend on the local models you configure. |
| Mem0/OpenMemory | Built-in | Hosted or self-hosted. | Self-hosting provides strongest control. |
| Zep/Graphiti | Partial | Hosted Zep or Graphiti library. | Verify platform retention and graph data handling. |
| Cognee | Built-in in local mode | SDK/local mode, optional Docker MCP setup, or API/Cloud mode. | Shared API mode changes control boundary. |
| Khoj | Built-in with self-hosting | Cloud or self-hosted. | Cloud convenience changes control boundary. |
| Obsidian/Logseq + AI bridge | Built-in | Local vault/graph and backups. | Plugin permissions can expand risk. |
| ChatGPT Memory | Partial | ChatGPT memory settings, deletion controls, Temporary Chat, and connected-app/source management. | Platform-bound and not portable by default; fully removing personalization context may require deleting related chats, files, or connected-app data. |
| Claude Projects/Claude Code | Partial | Plan, project, sharing, and workspace controls. | Project knowledge remains Claude-scoped. |
| NotebookLM | Partial | Hosted notebook controls and source management. | No local deployment for ordinary users. |

## Sources

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Hyperspell website](https://www.hyperspell.com/)
- [Honcho repository](https://github.com/plastic-labs/honcho)
- [Mnemosyne configuration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/configuration.md)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Mem0 open-source overview](https://docs.mem0.ai/open-source/overview)
- [Khoj docs](https://docs.khoj.dev/)
