# taOSmd

## Snapshot

- Website / repo: https://github.com/jaylfc/taosmd
- Company / maintainer: jaylfc
- Status: Active public repo
- Open source: Yes, MIT (LICENSE file present)
- Deployment: Fully local / offline, SQLite-backed; ONNX MiniLM embeddings on CPU or RK3588 NPU, optional GPU; no cloud and no API keys
- Primary users: Local-first and offline builders running agent memory on small or low-end hardware
- Best second-brain role: Local/offline agent memory layer with a benchmarked retrieval and correction loop
- Last reviewed: 2026-06-07
- Reviewed evidence: maintainer's public repo at https://github.com/jaylfc/taosmd (master), the `LICENSE` file (MIT), and maintainer-published benchmark reports in the repo

## One-line Summary

taOSmd is a fully local, SQLite-backed agent memory system that records an append-only transcript of both sides of an agent's work, derives a typed temporal knowledge graph and vector store from it, and serves hybrid retrieval through CLI, Python SDK, a local REST API, and an MCP server.

## Second-Brain Fit

taOSmd is best understood as a local/offline memory engine for AI agents rather than a no-code notes app or a hosted memory service. It targets readers who want benchmarked memory that runs on small local models and low-end hardware, owns its data on local disk, and treats an immutable transcript as ground truth. It is not a polished knowledge GUI and has no hosted/managed option by design.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Fully local/offline, SQLite-backed. Embeddings run on ONNX MiniLM (CPU) or RK3588 NPU, with optional GPU. No cloud dependency and no API keys. |
| Context capture | Append-only, read-only Archive of both sides of a session: user and agent messages, tool calls and results, decisions, and errors. Optional opt-in user activity/browsing capture, a Python `ingest()` path, and typed loaders. |
| Knowledge organization | A Librarian derives memory from the archive into a typed temporal knowledge graph (entities, triples, a closed predicate vocabulary) plus a vector store, with EDU/event extraction. |
| Memory evolution | Contradiction detection and invalidation (a corrected singular fact supersedes the old one; recall returns only the active fact), near-duplicate detection (Jaccard), retention scoring with promotion gates, reflect/consolidation, and a human review queue. |
| Retrieval / use | Hybrid retrieval via RRF over BM25 and vector search plus conversational adjacency, with an optional cross-encoder rerank stage. |
| Agent activation / write-back | Built-in CLI (`taosmd`), Python API/SDK, a local HTTP/REST API (`taosmd serve`, stdlib server bound to 127.0.0.1), and an MCP server (`taosmd mcp`, stdio; `mcp` optional extra). |
| Personal / team scope | Per-agent isolated indexes via an agent registry. No enforced multi-user RBAC; team scoping is per-agent isolation, not enforced roles. |
| Feedback / correction | Human review/correction queue; contradiction-driven supersede on the typed-KG layer; the immutable transcript provides provenance and audit. |
| Privacy / control | Fully local data ownership on disk; user-activity capture is opt-in; the append-only transcript gives a verifiable audit trail. No cloud egress by default. |
| Setup / operations | `pip install taosmd`, plus a local ONNX embedder and a small local LLM via Ollama or rkllama. The pip package install and CLI (`taosmd`/`serve`/`mcp`) are verified on a clean environment; the one-line bootstrap that pulls Ollama and downloads models is still being validated on clean machines. |

## Strengths

- Fully local and offline by design, with no cloud dependency and no API keys.
- Runs on small local models and low-end hardware, including RK3588 NPU embeddings.
- Append-only, read-only transcript of both sides of a session acts as ground-truth provenance and audit.
- Corrections supersede stale facts on the typed-KG layer, so recall returns only the active fact.
- Multiple shipped activation surfaces: CLI, Python SDK, local REST API, and MCP server.
- Hybrid retrieval (RRF + BM25 + vector + conversational adjacency) with optional cross-encoder rerank.
- Maintainer-published benchmarks are pinned to commit, judge, and dataset for reproducibility.

## Limitations

- Heavier dependency footprint than zero-dependency options (local embedder and a local LLM are needed).
- No hosted or managed option by design.
- No GUI; inspection and correction happen through the CLI, SDK, API, and the review queue.
- Team scoping is per-agent isolation, not enforced multi-user RBAC.
- Correction-supersede applies to the typed-KG layer; raw vector chunks are not invalidated.
- The full bootstrap-script clean-machine run (Ollama plus model downloads) is still being validated.

## Best For

- Local-first and offline users who cannot or do not want to send memory to the cloud.
- Builders running agent memory on small or low-end hardware, including single-board computers.
- Users who want a benchmarked retrieval and correction loop they can reproduce.
- Developers who want CLI, SDK, REST, and MCP access to the same local memory store.

## Not Ideal For

- Users who want the lowest possible setup burden or a zero-dependency install.
- Teams that need enforced multi-user RBAC and shared-memory governance.
- Users who want a hosted, managed, or no-code GUI experience.

## Tradeoffs

taOSmd trades hosted convenience and a polished GUI for full local ownership, offline operation on small hardware, and a reproducible benchmarked memory loop. It is a better fit when readers want to own the storage, run on local models, and keep an append-only audit trail than when they want fast hosted setup or enforced team governance. Benchmarks are maintainer-published and measured on a low-end reference stack under a strict local judge, so they describe behavior at that tier rather than independent third-party validation.

## Official Setup / Evaluation Links

- [taOSmd GitHub repo](https://github.com/jaylfc/taosmd)
- [taOSmd README](https://github.com/jaylfc/taosmd/blob/master/README.md)
- [taOSmd LICENSE (MIT)](https://github.com/jaylfc/taosmd/blob/master/LICENSE)

## Sources

- [taOSmd GitHub repo](https://github.com/jaylfc/taosmd)
- [taOSmd README](https://github.com/jaylfc/taosmd/blob/master/README.md)
- [taOSmd LICENSE (MIT)](https://github.com/jaylfc/taosmd/blob/master/LICENSE)
- Maintainer-published benchmark reports in the taOSmd repo: 97.0% end-to-end judge accuracy on LongMemEval-S measured on a low-end reference stack under a strict local judge, and a same-tier LoCoMo result under a dual-judge methodology, with commit, judge, and dataset pinned for reproducibility.
