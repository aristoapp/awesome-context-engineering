# Watchlist

These projects are relevant to AI second-brain architecture but are not yet full-profile entries in this repo. Move a project into `solutions/` only after source-backed research and clear official setup/evaluation links are ready.

| Project | Why it matters | Current status |
|---|---|---|
| Letta / MemGPT | Stateful agent architecture with memory blocks, archival memory, and agent-managed context. | Baseline candidate for agent-framework memory. |
| Mem.ai | AI notes app with API/MCP and consumer knowledge assistant positioning. | Candidate for AI notes / PKM product category. |
| Tana | Structured knowledge graph notes with Supertags and AI commands. | Candidate for schema-heavy PKM category. |
| Reflect | Encrypted AI notes app with backlinks and graph-oriented notes. | Candidate for AI notes / PKM category. |
| Capacities | Object-based knowledge studio. | Candidate for object-centric PKM category. |
| TideMind | Local-first AI second-brain positioning with knowledge graph claims. | Emerging local-first candidate. |
| Dory | Local-first shared memory daemon for MCP-aware agents. | Emerging local-first second-brain candidate. |
| Open Second Brain | Obsidian-native memory layer for agents. | Emerging Obsidian/MCP candidate; separate from OpenHuman. |
| MAGI | Persistent memory for AI agents. | Emerging AI-memory candidate. |
| [AccInt](https://github.com/maxbaluev/accreted-intelligence) | Local-first Work Model for coding agents that records commitments, approval gates, outcomes, and reusable runtimes, then uses outcome-scored memory to predict and replay verified paths through MCP. | Emerging agent-memory candidate for Use/Govern workflows; public repo ships installer/docs/plugins while the core memory engine is currently distributed as a private binary, so it is not yet a full evaluated profile. |
| [tracecraft](https://github.com/Arrmlet/tracecraft) | Serverless multi-agent coordination substrate using S3-compatible or Hugging Face storage for shared state, task claims, handoffs, and session traces. | Emerging coordination-substrate candidate; adjacent to agent memory but not a memory layer or second-brain system itself. |
| [screenpipe](https://github.com/screenpipe/screenpipe) | Local-first 24/7 screen and microphone capture daemon that indexes OCR, accessibility, and audio transcripts into a queryable SQLite store, with MCP, REST, and SDK access for AI tools and agents. | Emerging local-first context-collection candidate; covers the Collect lifecycle stage for second-brain workflows but leaves knowledge organization and memory evolution to layers above it. |
| [Off Grid AI Desktop](https://github.com/off-grid-ai/off-grid-ai-desktop) | On-device macOS app that captures screen frames to OCR and entities, keeps observations and memory in local SQLite, runs RAG search and chat over your own data through a bundled local LLM (llama.cpp), and adds MCP connectors with approval-gated actions, on-device image generation, and whisper voice dictation - no account, no telemetry, no cloud. | Emerging local-first candidate spanning Collect, Organize, and Use lifecycle stages for a personal second brain; AGPL-3.0 with a paid tier, verifiable from the public repo and product site, not yet a full evaluated profile. |

## Promotion Rule

A watchlist item can become a core profile when it has:

- official docs or repo evidence
- deployment model
- setup burden and official setup links
- AI-tool activation surface
- context capture and retrieval/use model
- known limitations
- tradeoffs
