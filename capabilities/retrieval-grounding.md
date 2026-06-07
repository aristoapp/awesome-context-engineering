# Retrieval / Use

## What This Capability Means

Retrieval and use cover how the system finds relevant memory, whether it can preserve source context, and whether people or AI tools can apply that context during real work.

## Evaluation Questions

- Does retrieval use keyword search, vector search, graph retrieval, RAG, or a hybrid model?
- Are source, timestamp, project, collection, and permission signals available at retrieval time?
- Can users or AI tools cite or inspect the source behind a memory?
- Can users distinguish fresh source data from stale, imported, or inferred memory?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Built-in | Graph + vector hybrid RAG for Memory with source/project/date filters; vector + keyword hybrid search for Wiki with collection scoping. | Dashboard chat and connected agents can use both stores; verify source availability for the target account. |
| OpenHuman | Built-in | Local Memory Tree, Obsidian-compatible Markdown vault, memory graph, and context compression. | Source/provenance behavior needs hands-on verification. |
| GBrain | Built-in | `search` for cheap hybrid retrieval, `query` for expanded hybrid retrieval with filters, graph/link signals, timeline/fact retrieval, and `think` synthesis with citations, conflicts, and gap analysis. | Quality depends on sync, embeddings, curated source structure, and reranker/provider configuration. |
| taOSmd | Built-in | Hybrid retrieval via RRF over BM25 and vector search plus conversational adjacency, with an optional cross-encoder rerank stage; the transcript provides source/provenance behind recalled facts. | Quality depends on the local embedder/LLM and rerank configuration; correction-supersede excludes stale facts from recall across both the typed-KG and vector layers, so retrieval returns only the active fact. |
| Hermes Agent + LLM Wiki | Built-in | The skill orients on `SCHEMA.md`, `index.md`, and `log.md`, searches files, reads relevant pages, synthesizes answers from compiled wiki pages, and can file valuable answers back into the wiki. | Not a vector DB or graph RAG engine by default; freshness depends on wiki maintenance. |
| Supermemory | Built-in | Hybrid search across extracted memories and document chunks, graph memory, project/container scoping, metadata, and API filters. | Connector and project scoping must be configured carefully. |
| Hyperspell | Built-in | Indexed search, live search, multi-source query, metadata/date/resource filters, source weighting, LLM-ready summaries, optional answer generation, and MCP search/get tools. | Indexed/live availability depends on source; beta integrations and query behavior should be verified per account. |
| Honcho | Built-in | Hybrid search, context retrieval, peer/session representations, peer cards, conclusions, and natural-language context queries. | Source metadata and citation UX depend on how the app or agent writes data into Honcho. |
| Mem0/OpenMemory | Built-in | Layered memory search with user IDs, run IDs, and metadata. | App owners define grounding and source metadata quality. |
| Zep/Graphiti | Built-in | Temporal knowledge graph, facts, episodes, and Graph RAG. | Best when application data is modeled explicitly. |
| Cognee | Built-in | Knowledge graph memory and recall tools. | Retrieval quality depends on ingestion and graph processing mode. |
| Khoj | Built-in | Natural-language search and chat over files and notes. | Strong source Q&A, weaker as a broad second-brain layer across tools. |
| Obsidian/Logseq + AI bridge | Integration | Local search, backlinks, graph views, and bridge-provided RAG/search. | Grounding quality depends on the selected bridge. |
| ChatGPT Memory | Partial | Platform memory, chat history reference, and supported Memory Sources. | Source and retrieval internals are platform-controlled and plan/region dependent. |
| Claude Projects/Claude Code | Built-in | Project knowledge search/RAG and Claude context surfaces. | Grounding is scoped to Claude contexts and plan behavior. |
| NotebookLM | Built-in | Source-grounded notebook retrieval and source selection. | Strong for bounded source sets, weak as a live second brain across workflows. |

## Sources

- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell manual integration](https://docs.hyperspell.com/core/integration)
- [Hyperspell MCP overview](https://docs.hyperspell.com/advanced/mcp-overview)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)
