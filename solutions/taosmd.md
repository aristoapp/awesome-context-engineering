# taOSmd

## Snapshot

- Website / docs: https://github.com/jaylfc/taosmd
- Company / maintainer: jaylfc (part of the taOS ecosystem)
- Status: Active public repo
- Open source: Yes
- Deployment: Local / offline, SQLite-backed. Embeddings via ONNX MiniLM on CPU, or RK3588 NPU (via QMD); optional GPU. No cloud dependency, no API keys.
- Primary users: Local-first, offline, and low-end / multi-machine agent builders who want benchmarked memory that runs on small local models rather than a frontier model.
- Best second-brain role: Local-first, benchmarked agent memory built on a full append-only transcript
- Last reviewed: 2026-06-05
- Reviewed evidence: official repo `master` (commit 7f798aa), README, and code under `taosmd/archive.py`, `taosmd/knowledge_graph.py`, `taosmd/vector_memory.py`, `taosmd/retrieval.py`, `taosmd/catalog_pipeline.py`, and `taosmd/cli.py`; LongMemEval-S and LoCoMo results in `docs/benchmarks.md`.

## One-line Summary

taOSmd records the full interaction into an append-only, read-only transcript, then derives a typed knowledge graph and vector memory from it, with correction-aware recall, tuned to run on small local models on modest or air-gapped hardware.

## Second-Brain Fit

taOSmd is best understood as a local memory engine for agents rather than a notes app or a hosted API. It keeps a verbatim ground-truth ledger of everything that happened (both sides of the conversation, tool calls and their results, decisions, errors), and a librarian pass turns that into structured, retrievable knowledge. It targets the low-end and offline tier: 8 GB RAM and Python are enough, and quality is benchmarked on small local models rather than hosted frontier models.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Fully local and offline; SQLite-backed; CPU (ONNX) embeddings, with NPU (RK3588) or GPU optional. No cloud dependency or API keys. |
| Context capture | Built-in append-only Archive capturing the full transcript: user and agent messages, tool calls and their results, API calls, decisions, errors, and opt-in user activity (app usage, content views, searches, browsing). Plus a Python `ingest()` API and typed loaders. |
| Knowledge organization | Typed temporal knowledge graph (entities, triples, closed predicate vocabulary), a vector store, EDU/event extraction, and a librarian layer that derives memory from the archive and bridges category-to-specific-name vocabulary gaps. |
| Memory evolution | Contradiction detection with invalidation: a corrected singular fact supersedes the old value, and recall returns only the active fact. Pass-2 typed event lift and reflect/consolidation; low-confidence conflicts are deferred to a human review queue. The raw archive is never mutated. |
| Retrieval / use | `retrieve()` with hybrid retrieval (RRF over vector + BM25), conversational adjacency, optional cross-encoder rerank, and intent-aware routing. Benchmarked recipes in `docs/benchmarks.md`. |
| Agent activation / write-back | Built-in CLI (`taosmd`) and a Python API/SDK (`ingest`, `search`, `retrieve`, plus `VectorMemory`/`KnowledgeGraph`/`Archive` classes). MCP server: work in progress (issue #84). Local HTTP/REST API: work in progress (issue #85). |
| Personal / team scope | Per-agent isolated indexes via the agent registry, plus a global memory-model config. Enforced multi-user RBAC is not present. |
| Feedback / correction | Contradiction-invalidation plus a `taosmd review` queue for human resolution of deferred conflicts. Because memory is derived from an immutable transcript, any memory can be traced back to and re-derived from source events. |
| Privacy / control | Strong. Fully local and offline; you own all data. User activity capture is opt-in. |
| Setup / operations | `pip install` plus a local ONNX embedder and a small local LLM (Qwen3-4B via Ollama or RK3588 RKLLM) for extraction/answering. Minutes once dependencies are in place. The maintainer notes the one-line install scripts are new and still being verified on clean environments. |

## Strengths

- Keeps a full, append-only, read-only transcript of both sides (messages, tool calls and results, decisions, errors, opt-in user activity) as a ground-truth ledger, giving strong provenance and audit that most consolidate-and-discard systems lack.
- Memory is derived from that immutable transcript by a librarian, not self-reported by the agent, which structurally avoids the self-reinforcing "the agent decided this matters" pollution loop.
- Corrected facts supersede old ones and recall returns only the active value, so corrections stop resurfacing.
- Benchmarked, with a reproducible methodology: 97.0% end-to-end Judge on LongMemEval-S and a same-tier leader result on LoCoMo, measured on small local models at a documented compute tier (commit-pinned numbers in `docs/benchmarks.md`).
- Designed for modest, multi-machine, and air-gapped deployments: runs on 8 GB RAM, no API keys, NPU or GPU optional.

## Limitations

- MCP and a local HTTP/REST API are still work in progress (issues #84 and #85); today's integration surfaces are the Python API/SDK and the CLI.
- Heavier dependency footprint (spaCy, onnxruntime, bm25s) than zero-dependency alternatives.
- No hosted or managed option by design, and no built-in graphical UI.
- Team scoping is per-agent isolation, not enforced role-based access control.
- Correction-supersedes-and-excludes-from-recall applies to the typed knowledge-graph fact layer; raw vector chunks are not invalidated.

## Best For

- Agents on low-end, offline, or air-gapped hardware that need real memory without a hosted model.
- Builders who want a verbatim, auditable record of everything (including tool results) as the source of truth, with structure derived on top.
- Multi-machine setups that pool several modest devices rather than one large box.

## Not Ideal For

- Teams needing a hosted, zero-ops managed memory service or enforced multi-tenant RBAC.
- Users who want a polished no-code notes UI.
- Workflows that require an MCP or HTTP API today (both are in progress).

## Tradeoffs

taOSmd trades a heavier local dependency footprint and a smaller set of ready integration surfaces for full data ownership, a complete auditable transcript, correction-aware recall, and benchmarked quality on small local models. It is a strong fit when local control, provenance, and small-hardware performance matter more than hosted convenience or one-click multi-language SDKs.

## Official Setup / Evaluation Links

- Repo and README: https://github.com/jaylfc/taosmd
- Benchmarks and methodology: https://github.com/jaylfc/taosmd/blob/master/docs/benchmarks.md

## Sources

- Official repo `master` (commit 7f798aa): README, `taosmd/archive.py`, `taosmd/knowledge_graph.py`, `taosmd/vector_memory.py`, `taosmd/retrieval.py`, `taosmd/catalog_pipeline.py`, `taosmd/cli.py`.
- `docs/benchmarks.md` for LongMemEval-S and LoCoMo results and methodology.
