# Feedback / Correction

## What This Capability Means

Feedback and correction cover whether users can see what the system knows, filter it by useful dimensions, correct bad memories, and verify that source imports or agent writes landed where expected.

## Evaluation Questions

- Can users browse, search, filter, edit, delete, or correct memory?
- Are source, date, project, collection, or workspace filters visible?
- Can users inspect ingestion, sync, connector, or indexing status?
- Is the primary interface built for humans, developers, agents, or all three?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Dashboard for sources, Chat in Dashboard, memories, Memory graph/table views, Wiki graph/table views, filters, and agent setup. | Memories can be browsed, moved to projects, and deleted, but not manually created/edited from the Memories tab yet; export, retention, and plan-specific governance should be verified. |
| OpenHuman | Built-in | Desktop UI, Memory Tree, Markdown vault, onboarding, voice, and app surfaces. | Early beta behavior should be tested directly. |
| GBrain | Partial | CLI plus HTTP admin surfaces for client registration, request logs, jobs, live activity, and scoped operations. | Useful for operations inspection, not a polished Notion/Roam-style knowledge UI. |
| Hermes Agent + LLM Wiki | Built-in in files | Users can inspect and edit Markdown pages, source folders, `index.md`, `log.md`, `SCHEMA.md`, frontmatter, confidence flags, and contradiction markers. | No polished hosted dashboard; review happens in files, editor, Obsidian, git, or similar tools. |
| Supermemory | Built-in | Hosted app, console, connector status, projects, and filters. | Team/admin inspection depends on plan and setup. |
| Hyperspell | Partial | Dashboard, list/get/update memory APIs, metadata filtering, indexing status, query errors, webhooks, evaluation API, and folder manual-review states. | End-user second-brain UI is mostly app-owned; verify dashboard visibility for target account. |
| Honcho | Partial | Developer-facing workspace, peer, session, conclusion, queue, and metadata tools through API/MCP. | Polished end-user review and correction UI is integration-owned. |
| Mnemosyne | Partial | CLI, export/import, update/delete/invalidate tools, diagnostics, scratchpad tools, and local SQLite files provide operator inspection paths. | No hosted human-facing review dashboard is documented as the primary surface. |
| taOSmd | Partial | A local web dashboard served by taosmd serve provides search, a pending-review list, and health; the CLI and append-only archive give operator inspection paths. | The dashboard is a local inspection surface, not a hosted multi-user review product. |
| Mem0/OpenMemory | Built-in | Platform dashboard and self-hosted dashboard/server paths. | Application owners still define user-facing review flows. |
| Zep/Graphiti | Partial | Developer/platform UI and graph APIs. | End-user second-brain UI is not the primary surface. |
| Cognee | Partial | Developer/admin surfaces and MCP tool references. | End-user inspection should be verified for the target workflow. |
| Khoj | Built-in | Web, desktop, browser, and editor/client interfaces. | Inspection depends on source and deployment choices. |
| Obsidian/Logseq + AI bridge | Built-in | Graph, backlinks, tags, properties, search, pages, and blocks. | Agent writes need review discipline. |
| ChatGPT Memory | Built-in | Settings, Manage memories, memory search/sort controls, memory history restore, and Memory Sources. | Only covers ChatGPT platform memory and supported platform sources. |
| Claude Projects/Claude Code | Built-in | Claude project UI, knowledge base, instructions, sharing controls, and RAG indicators. | Project visibility depends on workspace plan and permissions. |
| NotebookLM | Built-in | Notebook UI, sources panel, source selection, labels/categories, and generated artifacts. | Strong inspection for imported sources, not full second-brain operations. |

## Sources

- [Membase Memory](https://docs.membase.so/features/memory)
- [Membase Chat in Dashboard](https://docs.membase.so/features/chat)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell list memories](https://docs.hyperspell.com/api-reference/memories/list-memories)
- [Hyperspell folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)
- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)
