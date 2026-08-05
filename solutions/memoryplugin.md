# MemoryPlugin

## Snapshot

- Website / docs: https://www.memoryplugin.com/ and https://help.memoryplugin.com/
- Company / maintainer: MemoryPlugin (Crestify)
- Status: Active hosted product
- Open source: Hosted service is closed source; the local MCP server ([memoryplugin/mcp-server](https://github.com/memoryplugin/mcp-server), MIT) and the agent skill ([memoryplugin/agent-skills](https://github.com/memoryplugin/agent-skills)) are open source
- Deployment: Hosted SaaS, accessed through a browser extension, a hosted MCP server, a local MCP process, and a REST API
- Primary users: People who use several AI chat tools and want one shared memory across them, plus developers who want that memory in MCP clients
- Best second-brain role: Hosted cross-tool personal memory layer via browser extension, MCP, and API
- Last reviewed: 2026-08-05

## One-line Summary

MemoryPlugin is a hosted memory layer that gives 21+ AI chat tools and MCP clients one shared long-term memory, and makes imported ChatGPT, Claude, TypingMind, and Grok chat history recallable with cited sources.

## Second-Brain Fit

MemoryPlugin fits when the main problem is that context is fragmented across many AI chat tools. The browser extension injects and captures memory directly inside [21+ supported platforms](https://help.memoryplugin.com/platforms/supported-platforms) (ChatGPT, Claude, Gemini, Grok, Perplexity, DeepSeek, and others), and the same memory is available to coding agents and MCP clients through a hosted remote MCP server or a local open-source MCP process. Its chat-history feature imports existing conversation exports so years of prior AI conversations become recallable context rather than dead archives.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted SaaS. The extension and MCP servers talk to the hosted API; there is no self-hosted or local-only storage option. |
| Context capture | Built-in: save by asking the AI, highlighting text, or typing in the extension ([save flows](https://help.memoryplugin.com/questions/save-a-memory)); [chat-history import](https://help.memoryplugin.com/questions/import-chat-history) from ChatGPT, Claude, TypingMind, and Grok exports plus [hourly background auto-sync](https://help.memoryplugin.com/questions/enable-auto-sync) per platform; [ChatGPT saved-memory import](https://help.memoryplugin.com/features/chatgpt-memory-import); [image memories](https://help.memoryplugin.com/features/image-memories); [document uploads](https://help.memoryplugin.com/features/file-buckets); API ingestion. |
| Knowledge organization | Built-in [memory buckets](https://help.memoryplugin.com/features/memory-buckets) separate contexts; [Smart Memory](https://help.memoryplugin.com/features/smart-memory) organizes a bucket into AI-generated topic categories with summaries for context-aware loading; an early-beta [knowledge graph](https://help.memoryplugin.com/features/knowledge-graph) maps concepts in a bucket. |
| Memory evolution | Partial: [Memory Suggestions](https://help.memoryplugin.com/features/memory-suggestions) propose deduping, combining related memories, and updating stale ones, but a user approves each change; Smart Memory recategorizes as memories change. There is no autonomous consolidation or dream loop. |
| Retrieval / use | Hybrid semantic plus keyword search over memories; Smart Memory category loading; [chat-history recall](https://help.memoryplugin.com/api-reference/endpoint/recall-chat-history) that synthesizes matching past conversations into a summary with per-conversation source citations; [Ask](https://help.memoryplugin.com/features/ask) queries chat history, memories, and files from one interface; [auto-inject](https://help.memoryplugin.com/questions/auto-inject-memories) starts new chats with memory without a click. |
| Agent activation / write-back | Built-in: browser extension injection on 21+ platforms; [remote MCP server](https://help.memoryplugin.com/integrations/remote-mcp-server) over HTTP/SSE with OAuth 2.0 (PKCE and DCR); open-source [local MCP server](https://help.memoryplugin.com/integrations/mcp-server) (`npx @memoryplugin/mcp-server`); [official Custom GPT](https://help.memoryplugin.com/integrations/custom-gpt) and [build-your-own GPT Actions](https://help.memoryplugin.com/integrations/custom-gpt-integration); [TypingMind plugin](https://help.memoryplugin.com/integrations/typingmind-plugin); an [agent skill](https://github.com/memoryplugin/agent-skills) for coding agents; [REST API with an OpenAPI spec](https://help.memoryplugin.com/integrations/api-integration). Agents can store, search, update, and move memories and create buckets, not just read. |
| Personal / team scope | Partial: buckets separate personal, project, and topic contexts; [shared buckets](https://help.memoryplugin.com/features/shared-buckets) let users share a bucket with another person, set permissions, and see who added what. There is no organization or workspace product. |
| Feedback / correction | Built-in [dashboard](https://help.memoryplugin.com/features/dashboard) for viewing, editing, and deleting memories; [bulk operations](https://help.memoryplugin.com/features/bulk-operations); Memory Suggestions review; [per-chat opt-out](https://help.memoryplugin.com/questions/keep-a-chat-private) keeps a conversation away from memory, recall, and sync. |
| Privacy / control | Hosted controls: [memory export](https://help.memoryplugin.com/questions/export-my-memories) as CSV, JSON, or text; [import and export](https://help.memoryplugin.com/features/import-export) for portability; bulk memory deletion and conversation deletion via API; [API token rotation](https://help.memoryplugin.com/questions/find-api-token). Internal retrieval and ranking models: Not disclosed. |
| Setup / operations | Low. Install the extension or connect an MCP client and sign in; there is no infrastructure to operate ([quick setup](https://help.memoryplugin.com/getting-started/introduction)). |

## Strengths

- Broad chat-tool coverage: one memory injected natively into 21+ AI chat platforms via the extension, with the same memory reachable from Claude Code, Cursor, Codex, and other MCP clients.
- Chat-history import and hourly auto-sync turn existing ChatGPT, Claude, TypingMind, and Grok conversations into recallable, cited context.
- Nontechnical adoption path (extension plus dashboard) alongside developer surfaces (MCP, REST API, OpenAPI spec, agent skill).
- Portability: memories export as CSV, JSON, or text, and conversations are deletable via API.

## Limitations

- Hosted only; no self-hosted or local-only storage path.
- Memory evolution is user-approved suggestions rather than an autonomous consolidation loop.
- Team support stops at shared buckets with per-person permissions; there is no org workspace, RBAC, or admin product.
- The hosted service is closed source; only the local MCP server and agent skill are inspectable.

## Best For

- People who move between several AI chat tools daily and want each one to know the same context without re-explaining.
- Users with years of ChatGPT or Claude history who want it searchable and usable as context rather than archived.
- Mixed workflows where a nontechnical user works in the extension while coding agents use the same memory over MCP.

## Not Ideal For

- Users who require local-only or self-hosted memory storage.
- Teams that need workspace-level governance, roles, and admin controls.
- Builders who want an inspectable or self-operated memory substrate under their own application.

## Tradeoffs

MemoryPlugin optimizes for coverage and low setup burden across many AI chat tools rather than for local ownership or deep team governance. The extension-injection approach reaches chat platforms that have no API or MCP surface of their own, but the memory itself lives in the hosted service, so users who need local control should compare the local workspace and local-first agent memory options instead.

## Official Setup / Evaluation Links

- [Quick setup](https://help.memoryplugin.com/getting-started/introduction)
- [How MemoryPlugin works](https://help.memoryplugin.com/getting-started/how-it-works)
- [Supported platforms](https://help.memoryplugin.com/platforms/supported-platforms)
- [Browser extension](https://help.memoryplugin.com/integrations/browser-extension)
- [Remote MCP server](https://help.memoryplugin.com/integrations/remote-mcp-server)
- [Local MCP server](https://help.memoryplugin.com/integrations/mcp-server)
- [Chat history](https://help.memoryplugin.com/features/chat-history/introduction)
- [Smart Memory](https://help.memoryplugin.com/features/smart-memory)

## Sources

- [MemoryPlugin help docs](https://help.memoryplugin.com/)
- [Supported platforms](https://help.memoryplugin.com/platforms/supported-platforms)
- [Remote MCP server docs](https://help.memoryplugin.com/integrations/remote-mcp-server)
- [Chat-history recall API](https://help.memoryplugin.com/api-reference/endpoint/recall-chat-history)
- [Shared buckets](https://help.memoryplugin.com/features/shared-buckets)
- [Memory export](https://help.memoryplugin.com/questions/export-my-memories)
- [Open-source local MCP server](https://github.com/memoryplugin/mcp-server)
