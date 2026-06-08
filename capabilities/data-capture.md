# Context Capture

## What This Capability Means

Context capture is how raw personal, team, and source context enters the second brain: AI conversations, notes, documents, email, calendar, Slack, Drive, Notion, browser data, code, or custom events.

## Evaluation Questions

- Is capture built in, connector-based, API-based, or custom?
- Does capture preserve source, timestamp, and permissions?
- Does the system distinguish raw import from curated memory?
- Can users disconnect a source without losing needed history?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in + Integration | Agent writes, Chat in Dashboard, ChatGPT/Claude/Gemini chat import, Gmail/Google Calendar/Slack, Obsidian/Markdown Wiki import, and Notion import. | Notion sync, Drive, and GitHub should be treated as coming soon or verified in the target account before promising them. |
| OpenHuman | Built-in + Integration | 118+ OAuth integrations, auto-fetch, local Memory Tree, Markdown vault. | Beta behavior and connector reliability need hands-on verification. |
| GBrain | Built-in + Custom collector | Markdown import, `capture`, file/stdin capture, HTTP `/ingest`, inbox folder, `sync --watch` polling, recipes, and skillpack ingestion sources. | External APIs require recipe/custom collector work; `sync --watch` is polling, not streaming. |
| Hermes Agent + LLM Wiki | Built-in source workflow | The bundled skill defines capture paths for URLs, PDFs, pasted text, files, articles, papers, transcripts, and assets into `raw/`. | Not a broad OAuth connector layer; source gathering is agent/user workflow driven. |
| Supermemory | Built-in + Integration | MCP/API plus Drive, Gmail, Notion, OneDrive, GitHub, Web Crawler. | Connector permissions, sync state, and container/project tags matter. |
| Hyperspell | Built-in + Integration | Hyperspell Connect, workspace integrations, manual add, bulk ingestion, file upload, web crawler, folder sync policies, and trace ingestion. | Private beta/account availability varies; app owners still choose sources, metadata, and user scoping. |
| Honcho | API + Integration | API/SDK/MCP writes add messages, sessions, and uploaded documents. | Broad external source capture depends on the integrating app or agent. |
| Mnemosyne | API + Integration | MCP/CLI/SDK writes, Python `remember`, memory banks, and Hermes lifecycle hooks can capture agent context. | Not a broad OAuth connector layer; capture is agent, hook, or developer driven. |
| taOSmd | API + Integration | Python API, HTTP/REST, and MCP writes record each turn verbatim into an append-only archive, with vector and knowledge-graph indexing layered on top. | Capture is agent and developer driven, not a broad OAuth connector layer. |
| Mem0/OpenMemory | API + Integration | SDK/API/MCP writes from app or AI workflow. | Capture design is application-owned. |
| Zep/Graphiti | API | Chat history, business data, graph endpoints. | Requires app integration. |
| Cognee | Built-in + API | MCP memory/data tools and graph processing. | Standalone vs shared mode affects where data lands. |
| Khoj | Built-in | Files, notes, PDFs, Markdown, org-mode, Notion pages. | Better for personal source Q&A than broad cross-tool capture. |
| Obsidian/Logseq + AI bridge | Built-in notes + Integration | Local notes plus plugin/import/filesystem bridge. | Agent-ready capture depends on the bridge. |
| ChatGPT Memory | Built-in + platform sources | Saved memories, reference chat history, and supported Memory Sources such as custom instructions, files, and connected Gmail depending on plan, region, and settings. | Not a general external source-ingestion backend. |
| Claude Projects/Claude Code | Built-in | Project uploads, project instructions, chat context, and enabled connectors. | Capture is Claude-scoped unless external memory is added. |
| NotebookLM | Built-in | Upload/import/discovery for docs, PDFs, web URLs, YouTube, audio, Gemini Chats, Fast Research, Deep Research, and other supported source types. | Imported sources can be bounded/static depending on source type; supported Drive sources can auto-sync. |

## Sources

- [Membase overview](https://docs.membase.so/)
- [Membase app integrations](https://docs.membase.so/connectors/apps)
- [Membase Obsidian connector](https://docs.membase.so/connectors/obsidian)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Supermemory connectors](https://supermemory.ai/docs/connectors/overview)
- [Hyperspell integrations](https://docs.hyperspell.com/integrations/overview)
- [Hyperspell Connect](https://docs.hyperspell.com/usage/connect)
- [Honcho overview](https://honcho.dev/docs/v3/documentation/introduction/overview)
- [Mnemosyne docs](https://docs.mnemosyne.site/)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Khoj docs](https://docs.khoj.dev/)
