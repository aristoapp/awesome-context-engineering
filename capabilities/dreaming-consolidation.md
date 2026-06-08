# Memory Evolution

## What This Capability Means

Memory evolution is the ongoing work that keeps a second brain useful after capture: summarization, deduplication, fact repair, stale embedding repair, source cleanup, pruning, reflection, or synthesis.

## Evaluation Questions

- Is there a named maintenance or evolution loop?
- Is it product-managed, user-operated, or custom?
- Does it repair retrieval quality or only summarize?
- Can users inspect proposed changes before they become durable memory?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Smart digesting and managed product updates. | Schedule/internal mechanics are product-managed. |
| OpenHuman | Partial | Auto-fetch every 20 minutes, memory collapse, background thinking. | Not yet verified as a durable curated-knowledge loop. |
| GBrain | Built-in | `gbrain dream` maintenance cycle, `gbrain autopilot`, sync/embed jobs. | User operates jobs and verifies quality. |
| Hermes Agent + LLM Wiki | Partial | The bundled skill defines re-ingest, source drift checks, query filing, lint, archive, page splitting, and log rotation. | Not an autonomous maintenance loop by default; user or Hermes automation must trigger upkeep. |
| Supermemory | Built-in | Product-managed graph memory updates, relationship tracking, and automatic forgetting. | Not exposed as a user-operated dream loop. |
| Hyperspell | Built-in + Partial | Connected memories update when source data changes; procedural memory extracts reusable steps from agent traces; homepage claims query/conversation reinforcement. | Exact consolidation and reinforcement mechanics are product-managed and should be verified for the target account. |
| Honcho | Built-in | Background reasoning updates peer representations and conclusions; MCP exposes `schedule_dream`. | Mechanics are system-managed; user review depends on the integration. |
| Mnemosyne | Built-in | `sleep` and BEAM consolidation move working memory toward episodic memory; Hermes integration exposes consolidation commands. | Users still decide when to run consolidation and how to validate durable memory quality. |
| taOSmd | Partial | Correction and supersede stop superseded facts from being recalled across the graph and vector layers, and a retention score ages memory. | There is no scheduled dream or consolidation cycle, and the raw archive is always retained. |
| Mem0/OpenMemory | Partial | Memory promotion/search behavior and platform processing. | Explicit consolidation policy is app-owned. |
| Zep/Graphiti | Built-in | Temporal graph updates, facts, summaries. | Application must ingest updates correctly. |
| Cognee | Built-in | `improve` and graph processing workflows. | Terminology differs from dreaming. |
| Khoj | Partial | Indexing and assistant workflows. | No central dream loop in this repo's current evaluation. |
| Obsidian/Logseq + AI bridge | Custom collector | Nightly scripts, plugins, or external memory services. | User owns review and write-back safety. |
| ChatGPT Memory | Built-in | Platform-managed memory behavior. | Not exposed as a user-operated maintenance loop. |
| Claude Projects/Claude Code | Built-in | Platform RAG/project knowledge behavior. | Not a user-operated dream loop. |
| NotebookLM | Partial | Summaries and generated artifacts. | Not an ongoing second-brain maintenance loop. |

## Sources

- [Membase overview](https://docs.membase.so/)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell procedural memory](https://docs.hyperspell.com/usage/procedural-memory)
- [Hyperspell core concepts](https://docs.hyperspell.com/core/concepts)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Mnemosyne repository](https://github.com/AxDSan/Mnemosyne)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
