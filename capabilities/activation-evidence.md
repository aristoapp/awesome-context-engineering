# Activation Evidence

## What This Capability Means

Activation evidence asks whether a second brain can prove that retrieved memory actually affected a human or AI workflow. It sits at the seam between Retrieval / Use and Govern: retrieval may return relevant context, but activation evidence shows what was loaded, cited, promoted, refused, or acted on during the work.

This capability is useful when comparing systems that all claim memory, RAG, MCP, or agent access. The question is not only "can the agent query memory?" but also "can the user audit what context crossed into the task and whether the agent relied on it safely?"

## Evaluation Questions

- Can the system show which memories, notes, files, facts, or graph nodes were retrieved for a specific task or session?
- Does the workflow distinguish candidate retrieval from context that was actually injected, opened, cited, or used by the AI tool?
- Can users see freshness, source, scope, and permission signals for activated context?
- Can the system mark context as stale, refused, out of scope, or unsafe to rely on?
- Is there a handoff artifact that lets a fresh agent answer: current decision, evidence, rejected options, stale risks, and next safe action?
- If AI tools can write back, can users tell which source or action caused a memory to be promoted, corrected, or deleted?

## Practical Activation Test

A small evaluation can be run without knowing a vendor's internal ranking logic:

1. Seed or identify one decision with a source, one rejected option, and one stale or superseded note.
2. Start a clean AI-tool session connected to the second brain.
3. Ask for the current decision, source evidence, rejected option, stale risk, and next safe action.
4. Check whether the answer cites activated context and marks the stale item correctly, instead of guessing from a polished summary.
5. If the agent performs work, inspect whether the retrieved context was actually cited, opened, written back, or reflected in the action.

Passing this test does not require exposing private memory text in logs. A system can use source IDs, hashes, timestamps, scopes, and short reason classes as the audit surface.

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Partial | Memory/Wiki retrieval and connected AI workflows create a place to inspect what context can be used. | Verify whether a specific workflow exposes per-session retrieved-vs-used evidence. |
| Hjarni | Partial | MCP `search`, `notes-get`, `notes-create`, and `notes-update` calls expose which notes were searched, read, created, or updated for a task; results carry note IDs, container paths, timestamps, and a `last_edited_by_agent` label. | Whether the agent actually relied on or cited that context (acted-on proof) still depends on the AI client's own logs. |
| GBrain | Partial | CLI/MCP workflows with citations, conflicts, and gap analysis can support activation checks. | Needs hands-on verification for per-session acted-on evidence. |
| Hermes Agent + LLM Wiki | Integration | Local Markdown wiki files make source inspection and handoff artifacts easy to audit. | Activation evidence depends on skill behavior and user discipline. |
| Supermemory | Partial | MCP/API retrieval can expose source-backed memory to agents. | App owners need to record which retrieved items were actually used. |
| Hyperspell | Partial | MCP search/get tools and metadata filters can provide context activation inputs. | Verify whether the host workflow records usage beyond retrieval. |
| Honcho | Partial | Session and peer context APIs can help explain what context was available to an agent. | Application integration determines whether acted-on evidence is captured. |
| Mnemosyne | Partial | MCP, CLI, and Hermes tool calls can show that recall or memory tools ran for a workflow. | Agent logs must still connect retrieved memories to decisions, citations, or write-back. |
| taOSmd | Partial | The append-only archive, the pending-review list, and the local dashboard show which turns and facts are stored and retrievable. | Agent logs must still connect retrieved memories to decisions, citations, or write-back. |
| Mem0/OpenMemory | Partial | User/run-scoped memory search can support activation traces. | Grounding and acted-on proof are usually app-level responsibilities. |
| Zep/Graphiti | Partial | Temporal graph facts and episodes provide source structure for task evidence. | The application must connect graph retrieval to action logs. |
| Cognee | Partial | Knowledge graph recall tools can return structured context for agents. | Verify host-level usage evidence per workflow. |
| Obsidian/Logseq + AI bridge | Integration | Local notes, backlinks, and file history are inspectable activation sources. | The bridge must record what was loaded and used. |
| ChatGPT Memory | Unknown | Platform-native memory can personalize a session. | Per-memory retrieval and acted-on evidence are platform-controlled. |
| Claude Projects/Claude Code | Partial | Project knowledge, files, skills, and tool logs can show parts of context activation. | Users may still need custom receipts or logs to separate loaded context from acted-on context. |
| NotebookLM | Built-in | Source-grounded answers and citations make activation evidence visible for bounded notebooks. | Limited to notebook source sets rather than broad live workflow memory. |

## Notes

Activation evidence is not the same as perfect observability. A practical second brain can start with minimal, privacy-safe receipts: context ID, source reference, freshness, task/session ID, action taken, and skipped/refused reason. This is often enough to decide whether the brain is trustworthy for handoff and workflow automation.

## Sources

- [Agent Activation / Write-back](agent-access.md)
- [Retrieval / Use](retrieval-grounding.md)
- [Privacy / Control](privacy-control.md)
- [Hjarni solution profile](../solutions/hjarni.md)
- [Hjarni MCP server repository](https://github.com/hjarni/hjarni-mcp)
- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [GBrain solution profile](../solutions/gbrain.md)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)
