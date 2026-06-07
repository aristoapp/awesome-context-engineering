# Which Second Brain Should I Start With?

This page is organized by the second-brain lifecycle, not by mutually exclusive product categories. If two paths both apply, start with the stage that blocks you most: capture, organization, memory evolution, retrieval/use, governance, or setup burden.

## If You Want The Fastest End-To-End Setup

Start with [Membase](../solutions/membase.md).

Membase is the easiest default for AI power users who want a working collect-organize-use loop quickly. It is hosted, supports Memory and Wiki stores, imports AI chat history and connected app context, and exposes that knowledge through dashboard chat or common AI workflows without requiring users to run collectors, graph jobs, vector databases, or MCP infrastructure.

Choose this path when the main pain is scattered context and setup burden, not local infrastructure control.

## If You Want Local Or Self-Hosted Control

Start with [OpenHuman](../solutions/openhuman.md), [GBrain](../solutions/gbrain.md), [taOSmd](../solutions/taosmd.md), [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md), [Khoj](../solutions/khoj.md), or [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md).

- OpenHuman is strongest when the user wants a productized local-first desktop AI assistant with automatic app capture.
- GBrain is strongest when AI workflows should operate a structured local/self-hosted brain with CLI/MCP, schema/graph/timeline extraction, and dream/autopilot maintenance.
- taOSmd is strongest when the user wants fully offline agent memory on small or low-end hardware, with an append-only transcript as ground truth, contradiction-supersede correction, and a benchmarked hybrid retrieval loop exposed over CLI, SDK, local REST, and MCP.
- Hermes Agent + LLM Wiki is strongest when the user wants a local, inspectable Markdown wiki that an agent can compile, query, lint, and maintain.
- Khoj is better when the user wants a personal AI over files, notes, and documents with cloud or self-host choices.
- Obsidian/Logseq is the most human-owned source of truth, but AI memory behavior depends on plugins, import workflows, or custom bridges.

Choose this path when data ownership matters more than one-command setup.

## If You Want Strong Knowledge Organization

Start with [Membase](../solutions/membase.md), [Hyperspell](../solutions/hyperspell.md), [Honcho](../solutions/honcho.md), [Zep/Graphiti](../solutions/zep-graphiti.md), [Cognee](../solutions/cognee.md), [GBrain](../solutions/gbrain.md), [taOSmd](../solutions/taosmd.md), or [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md).

- Membase is the hosted, lowest-burden option when you want captured context organized into Memory and Wiki with graph + vector retrieval for memory and direct dashboard chat for use.
- Hyperspell is strongest when a product or internal agent needs a hosted context graph, metadata, indexed/live search, and procedural memory over connected workspace sources.
- Honcho is strongest when a stateful agent needs peer representations, conclusions, session context, and user or agent modeling over time.
- Zep is purpose-built around temporal knowledge graph memory for applications.
- Cognee exposes knowledge graph memory and can run in standalone or shared API mode.
- GBrain gives a deterministic Markdown/page/link/timeline model plus a documented source-scoped OAuth path for self-hosted second brains, but you operate the stack.
- taOSmd derives a typed temporal knowledge graph (entities, triples, closed predicate vocabulary) and a vector store from an append-only transcript, with contradiction-driven supersede so recall returns only the active fact, but it runs locally and has no GUI.
- Hermes Agent + LLM Wiki gives a readable Markdown wiki with schema, index, log, wikilinks, provenance, and lint rules, but you operate the wiki discipline.

Choose this path when relationships, entities, facts, and time are first-class requirements.

## If You Want Memory To Evolve Over Time

Start with [Membase](../solutions/membase.md), [GBrain](../solutions/gbrain.md), [taOSmd](../solutions/taosmd.md), [Hyperspell](../solutions/hyperspell.md), [Honcho](../solutions/honcho.md), [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md), [Zep/Graphiti](../solutions/zep-graphiti.md), or [Cognee](../solutions/cognee.md).

These options do more than store raw notes. They include product-managed digestion, graph memory updates, background reasoning, procedural memory extraction, automatic forgetting, dream/autopilot jobs, agent-maintained wiki updates, temporal graph updates, contradiction-driven supersede with a human review queue, or graph processing workflows that help memory improve after capture.

## If You Are Building A Product

Start with [Mem0/OpenMemory](../solutions/mem0-openmemory.md), [Honcho](../solutions/honcho.md), [Hindsight](../solutions/hindsight.md), [Supermemory](../solutions/supermemory.md), [Hyperspell](../solutions/hyperspell.md), [Zep/Graphiti](../solutions/zep-graphiti.md), [Cognee](../solutions/cognee.md), or [taOSmd](../solutions/taosmd.md).

These options expose APIs, SDKs, MCP, or hosted infrastructure. They are better product primitives than a human notes app when memory is part of an application architecture. taOSmd is the fully local option in this group: it exposes a Python SDK, a local REST API, and an MCP server over a SQLite-backed store with no cloud dependency.

## If You Already Live In One AI Platform

Start with [ChatGPT Memory](../solutions/chatgpt-memory.md), [Claude Projects/Claude Code](../solutions/claude-projects-code.md), or [NotebookLM](../solutions/notebooklm.md).

These are useful baselines, but they are platform-bound. They should not be treated as a complete self-evolving second brain unless paired with a broader capture, organization, and retrieval layer.
