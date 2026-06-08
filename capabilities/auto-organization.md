# Knowledge Organization

## What This Capability Means

Knowledge organization is the system's ability to turn raw context into durable, reusable knowledge: summaries, entities, links, tags, schemas, graph edges, facts, timelines, or wiki pages.

## Evaluation Questions

- Does organization happen automatically or through explicit review?
- Are relationships deterministic, semantic, or LLM-inferred?
- Can users inspect and correct the result?
- Does the system separate raw data from curated knowledge?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Memory graph extraction plus linked Wiki documents and collections. | Memory retrieval also uses vector search; internal product behavior is managed by Membase. |
| OpenHuman | Built-in | Memory Tree, local SQLite knowledge base, Markdown vault, token compression, hierarchical summary trees, collapse flows. | Exact consolidation quality should be tested. |
| GBrain | Built-in | Schema packs, `gbrain-base-v2`, schema detect/suggest/review flows, page type inference, auto-linking, timeline/fact extraction, and takes. | Quality improves with structured Markdown, active schema selection, and review. |
| Hermes Agent + LLM Wiki | Built-in | Agent-maintained Markdown wiki with schema, index, log, raw sources, entity pages, concept pages, comparison pages, query pages, frontmatter, tags, wikilinks, confidence, and contradiction markers. | Organization quality depends on the agent following the skill and the user maintaining schema discipline. |
| Supermemory | Built-in | Processing pipeline, fact-based graph memory, relationship tracking, metadata/filtering. | Exact graph semantics should be verified per use case. |
| Hyperspell | Built-in | Memories, connected data sources, metadata filters, collections, structured resource data, LLM-ready summaries, context graph claims, and procedural memories from traces. | App owners still design taxonomy, metadata, review UI, and safe recall boundaries. |
| Honcho | Built-in | Workspaces, peers, sessions, messages, conclusions, representations, peer cards, and session context. | End-user organization and review UI depend on the integration. |
| Mnemosyne | Built-in | Working memory, episodic memory, scratchpad, memory banks, and a TripleStore for temporal graph-style facts. | Organization quality depends on memory scope design, embedding configuration, and agent write behavior. |
| taOSmd | Built-in | An append-only archive, a vector index, a temporal knowledge graph, and a librarian layer turn raw turns into retrievable structure. | Organization quality depends on the local extraction model, embedding configuration, and agent write behavior. |
| Mem0/OpenMemory | Built-in | Layered memory types and search/promotion model. | App must choose scope and metadata carefully. |
| Zep/Graphiti | Built-in | Entity nodes, entity edges, episodic nodes, facts, summaries. | Strong for temporal graph apps, not no-code PKM. |
| Cognee | Built-in | Knowledge graph memory tools and processing. | Graph quality depends on ingestion and processing. |
| Khoj | Built-in | Indexing/search over personal files and notes. | Less schema-heavy than graph memory systems. |
| Obsidian/Logseq + AI bridge | Partial | Tags, links, properties, blocks, and plugins. | AI organization is bridge-dependent. |
| ChatGPT Memory | Built-in | Platform-managed saved memories and chat history reference. | Organization is not developer-operable. |
| Claude Projects/Claude Code | Built-in | Project knowledge, instructions, and platform RAG behavior. | Structure is scoped to Claude project contexts. |
| NotebookLM | Built-in | Source summaries, labels/categories when enough sources exist, and generated artifacts. | Strong for bounded notebooks, not a live memory graph. |

## Sources

- [Membase overview](https://docs.membase.so/)
- [How Membase works](https://docs.membase.so/core-concepts/how-membase-works)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell core concepts](https://docs.hyperspell.com/core/concepts)
- [Hyperspell procedural memory](https://docs.hyperspell.com/usage/procedural-memory)
- [Honcho overview](https://honcho.dev/docs/v3/documentation/introduction/overview)
- [Mnemosyne docs](https://docs.mnemosyne.site/)
- [Mnemosyne repository](https://github.com/AxDSan/Mnemosyne)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
