# taOSmd

## Snapshot

- Website / docs: https://github.com/jaylfc/taosmd
- Repo: https://github.com/jaylfc/taosmd
- Release: https://github.com/jaylfc/taosmd/releases/tag/v0.3.0
- Company / maintainer: jaylfc (independent), part of the taOS ecosystem
- Status: Open-source Python package, tagged release v0.3.0, with Python API, CLI, local HTTP/REST, and MCP surfaces
- Open source: Yes, MIT-licensed repository (recognized by GitHub)
- Deployment: Local-first. Source install of a Python package (no PyPI release yet), running offline with local ONNX embeddings and a local LLM through Ollama, or an RK3588 NPU through RKLLM. Optional remote client mode points a local CLI at a shared `taosmd serve` instance over your own network.
- Primary users: Developers and agent operators who want an offline, local-first agent memory layer on modest or single-board hardware
- Best second-brain role: Local-first, offline agent memory layer with a zero-loss archive, source-linked verifiable recall, and maintainer-published retrieval benchmarks
- Last reviewed: 2026-06-21

## One-line Summary

taOSmd is a local-first, offline agent memory layer that stores every conversation turn verbatim in an append-only, zero-loss archive, then layers vector search, a temporal knowledge graph, and a librarian on top. Every extracted fact stays linked to the source span it came from, and a verifier can demote facts it cannot support so they are not served. It is exposed through a Python API, a CLI, a local HTTP/REST API, and an MCP server.

## Second-Brain Fit

taOSmd fits best as a developer- or operator-run memory backend for agents that need to run offline and on modest hardware. It is useful when the second brain must keep the source transcript byte-for-byte, run without a cloud API, and stay within the memory budget of a Raspberry Pi, an Intel mini PC, an old laptop, or a single-board computer with an NPU.

It is closest to Mnemosyne, Mem0/OpenMemory, Hindsight, Honcho, and Cognee in this repo's landscape: more programmable and local-first than hosted memory products, but less ready-made than an end-to-end second-brain app with built-in connectors, a wiki UI, and team governance. Its main point of difference from those peers is the append-only, zero-loss archive, a focus on offline operation on low-end hardware, and source-linked, verifiable memory: each fact traces back to its archived source, and the recall gate demotes facts a verifier marks unsupported instead of serving them.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Local-first. Source install of a Python package (no PyPI release yet); local SQLite stores, local ONNX embeddings, and a local LLM through Ollama, or an RK3588 NPU through RKLLM. An optional remote client mode targets a shared `taosmd serve` instance over your own network. |
| Context capture | API-, HTTP-, and MCP-driven. Each conversation turn is recorded verbatim into an append-only archive first; vector and knowledge-graph indexing are layered on top. Capture is agent and developer driven, not a broad OAuth connector layer. |
| Knowledge organization | Built-in append-only archive, a local vector index, a temporal knowledge graph, and a librarian retrieval layer over the stored turns. |
| Memory evolution | Correction and supersede mark facts as no longer recalled across both the knowledge graph and the vector layer, a retention score ages memory, and an optional recall gate demotes facts a verifier marks unsupported so they are not served while staying in the archive. There is no scheduled dream or consolidation cycle, and the raw archive is always retained. |
| Retrieval / use | Hybrid keyword and vector search with fusion and an optional reranker, plus the temporal knowledge graph and librarian. MCP, HTTP/REST, Python API, and CLI surfaces can retrieve context for agents. |
| Agent activation / write-back | Built-in MCP server over stdio, a local HTTP/REST API via `taosmd serve`, a Python API, and a CLI. Documented use covers Claude Code, OpenClaw, Cursor, and other MCP-compatible clients; the package ships a per-turn agent-rules block and a Claude Code skill. |
| Personal / team scope | Partial. Each agent gets its own shelf, with cross-agent reads, but team permissions and review workflows are not a product surface. |
| Feedback / correction | Correction and supersede operate across the knowledge graph and the vector layer while the raw archive row is retained, and a pending-review list surfaces low-confidence items. A verify pass checks each extracted fact against its archived source span and records the share that is not fully supported, which the project tracks as a standing metric (about 19% of regex-extracted facts on one dataset). |
| Privacy / control | Local-first and offline by default: local SQLite stores, local ONNX embeddings, a configurable data directory, and no cloud calls. Secrets are redacted on the A2A bus. Embedding and LLM behavior depend on the local models you configure. |
| Setup / operations | Medium. The verified path is a source install plus a local embedding model and a local LLM. There is no PyPI package yet, and retrieval and extraction quality depend on the local models and configuration you run. |

## Strengths

- Append-only, zero-loss archive: the verbatim turn is stored first, and summaries and structure are layered on top, never over the source.
- Runs offline on modest or single-board hardware, with an NPU path for RK3588 boards.
- Python API, CLI, local HTTP/REST API, and an MCP server are documented and verified to install from source on a clean machine.
- Per-agent shelves with cross-agent reads give developers isolation primitives.
- Correction and supersede span both the knowledge graph and the vector layer, while the raw archive is retained.
- Source-linked, verifiable memory: every extracted fact keeps a pointer to its archived source, a verifier checks each one, and the recall gate demotes facts it cannot support before they are served. On a 200-question LoCoMo slice this moved the served-unsupported rate from 0.04 to 0.00 at no measured accuracy cost (tri-judge).
- Reports its own extraction-error rate as a standing metric (about 19% of regex-extracted facts were not fully supported by their source on one dataset), rather than discarding the source after extraction.
- Maintainer-published benchmarks and methodology are included in the repository, with a public research report: 97% Recall@5 and 74.6% end-to-end Judge on LongMemEval-S, and 0.748 lenient (tri-judge) on LoCoMo, all reproducible from the recorded recipes.

## Limitations

- It is a memory backend, not a full consumer second-brain application.
- No PyPI package yet; the supported install today is from source. The one-line bootstrap that also installs the local LLM and models is still being validated on clean machines.
- Broad app connectors, a hosted dashboard, team permissions, and source governance are not the main product surface.
- Benchmark numbers are maintainer-run local results and should not be treated as independent third-party evaluation without reproduction.
- Retrieval and extraction quality depend on the local embedding and LLM models, configuration, and agent write behavior.

## Best For

- Developers who need an offline, local-first agent memory layer on a Raspberry Pi, a single-board computer, an Intel mini PC, an old laptop, or a small cluster.
- Agent operators who want MCP- or HTTP-accessible local memory without operating a hosted service.
- Workflows where the verbatim transcript must be retained byte-for-byte, even after summaries and corrections.
- Users who prefer local SQLite ownership over a managed memory platform.

## Not Ideal For

- Users who want a hosted dashboard, built-in OAuth connectors, and the lowest possible setup burden.
- Teams that need workspace permissions, admin controls, and a governance UI out of the box.
- Source-grounded research workflows where a bounded notebook or wiki is enough.
- Non-technical users who do not want to install from source or operate a local LLM and embedding model.

## Tradeoffs

taOSmd gives strong local control, an offline footprint that fits low-end hardware, and a zero-loss archive, but it shifts model operation and integration decisions to the user. There is no hosted option and no PyPI package yet, so the verified path is a source install plus a local LLM and embedding model. Compare it with Mnemosyne, Mem0/OpenMemory, Hindsight, Honcho, and Cognee when the primary need is local or programmable agent memory rather than a complete hosted second-brain product, and weight it higher when offline operation, low-end hardware, or a byte-for-byte source record matter most.

## Official Setup / Evaluation Links

- Repository: https://github.com/jaylfc/taosmd
- Release v0.3.0: https://github.com/jaylfc/taosmd/releases/tag/v0.3.0
- Benchmarks and methodology: https://github.com/jaylfc/taosmd/blob/master/docs/benchmarks.md
- Agent integration rules: https://github.com/jaylfc/taosmd/blob/master/taosmd/docs/agent-rules.md

## Sources

- https://github.com/jaylfc/taosmd
- https://github.com/jaylfc/taosmd/releases/tag/v0.3.0
- https://github.com/jaylfc/taosmd/blob/master/docs/benchmarks.md
- https://github.com/jaylfc/taosmd/blob/master/README.md
