# Which Second Brain Should I Start With?

This page is organized by the second-brain lifecycle, not by mutually exclusive product categories. Start with the lifecycle gap that blocks you most: collect, organize, evolve, use, or govern. If two paths both apply, solve the earlier lifecycle gap first, then use [Solution Layers](solution-layers.md) to understand whether you are adopting an app, local workspace, agent memory layer, substrate, or platform baseline.

## If Scattered Context Is Not Being Collected

Start with [Membase](../solutions/membase.md), [OpenHuman](../solutions/openhuman.md), [Supermemory](../solutions/supermemory.md), [Hyperspell](../solutions/hyperspell.md), [Khoj](../solutions/khoj.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Stigmergy](../solutions/stigmergy.md), or [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md).

- Membase is the low-ops hosted path when you want AI chats and connected sources to become usable Memory and Wiki without running local collectors or memory infrastructure.
- OpenHuman is strongest when the user wants a productized local-first desktop AI assistant with automatic app capture.
- Supermemory and Hyperspell are useful when collection needs to feed AI workflows, products, or agent-facing APIs.
- Khoj is better when the main sources are files, notes, documents, and web pages.
- obsidian-wiki is stronger when sources include coding-agent histories and the target is a shared, agent-maintained Obsidian vault rather than a hosted connector layer.
- Stigmergy collects where a team already works: an emoji reaction captures a Slack message verbatim, agents submit through MCP, and an operator CLI drops meeting transcripts. There is no platform-level connector catalog, and you host the service yourself.
- Obsidian/Logseq is strongest when human-owned local notes are the source of truth, but AI capture depends on plugins, imports, or custom bridges.

Choose this path when the first problem is that useful context is still scattered across tools.

## If Raw Context Needs Durable Structure

Start with [Membase](../solutions/membase.md), [Hjarni](../solutions/hjarni.md), [GBrain](../solutions/gbrain.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Stigmergy](../solutions/stigmergy.md), [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md), [Mnemosyne](../solutions/mnemosyne.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md), [Honcho](../solutions/honcho.md), [Zep/Graphiti](../solutions/zep-graphiti.md), or [Cognee](../solutions/cognee.md).

- Membase is the hosted, lowest-burden option when captured context should become Memory and Wiki with graph + vector retrieval for memory and dashboard chat for use.
- Hjarni keeps structure deliberate and inspectable: Markdown notes in a hierarchy of folders (containers), with tags, wiki-links, and per-folder AI instructions, authored by you or by an agent through MCP. The structure is hand-built rather than extracted automatically.
- GBrain gives a deterministic Markdown/page/link/timeline model plus a documented source-scoped OAuth path for self-hosted second brains, but you operate the stack.
- obsidian-wiki gives multiple coding agents a shared skill-based workflow for compiling sources and conversation history into one Obsidian vault, with provenance, delta tracking, graph-aware query, and maintenance tools.
- Stigmergy turns captures into Markdown pages in a git repository the team owns, with a page contract, an entity registry, resolved links and backlinks, and per-entity rollups; entity names are approved by a person rather than invented by the agent, which is aimed at the duplicate-entity problem in shared wikis.
- Hermes Agent + LLM Wiki gives a readable Markdown wiki with schema, index, log, wikilinks, provenance, and lint rules, but you operate the wiki discipline.
- Mnemosyne gives memory tiers, memory banks, hybrid retrieval, and temporal triples inside a local SQLite-backed agent memory layer.
- taOSmd keeps every conversation turn verbatim in an append-only archive, then layers vector search, a temporal knowledge graph, and a librarian on top, running offline on low-end hardware.
- Vestige gates writes with a prediction-error step that merges redundant and supersedes contradictory records, and keeps a memory graph with associations over local SQLite, as one Rust binary for coding agents.
- Honcho is strongest when stateful agents need peer representations, conclusions, session context, and user or agent modeling.
- Zep/Graphiti and Cognee are better read as graph or knowledge memory substrates for applications.

Choose this path when relationships, entities, facts, pages, links, and time are the main missing pieces.

## If Memory Needs To Evolve Over Time

Start with [Membase](../solutions/membase.md), [GBrain](../solutions/gbrain.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Hyperspell](../solutions/hyperspell.md), [Honcho](../solutions/honcho.md), [Hindsight](../solutions/hindsight.md), [Mnemosyne](../solutions/mnemosyne.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md), [Zep/Graphiti](../solutions/zep-graphiti.md), or [Cognee](../solutions/cognee.md).

These options do more than store raw notes. They include product-managed digestion, graph memory updates, background reasoning, procedural memory extraction, automatic forgetting, dream/autopilot jobs, memory-bank consolidation, temporal graph updates, graph processing workflows, or agent-operated deduplication and maintenance that help memory improve after capture. Vestige is in this group for its FSRS-6 decay, prediction-error gated writes, consolidation/dream maintenance, dedup, and reversible active forgetting.

Choose this path when stale, duplicated, or disconnected memory is the main problem.

## If Context Needs To Show Up Inside AI Tools

Start with [Membase](../solutions/membase.md), [Hjarni](../solutions/hjarni.md), [Supermemory](../solutions/supermemory.md), [Hyperspell](../solutions/hyperspell.md), [Honcho](../solutions/honcho.md), [Hindsight](../solutions/hindsight.md), [Mnemosyne](../solutions/mnemosyne.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Stigmergy](../solutions/stigmergy.md), [Mem0/OpenMemory](../solutions/mem0-openmemory.md), or [Claude Projects/Claude Code](../solutions/claude-projects-code.md).

- Membase exposes organized knowledge through dashboard chat and connected AI workflows without asking the user to operate MCP infrastructure first.
- Hjarni exposes your notes to Claude and ChatGPT through a built-in remote MCP server (OAuth) and a REST API, so agents can search, read, create, and update notes during a task.
- Supermemory, Hyperspell, Honcho, Hindsight, Mnemosyne, taOSmd, Vestige, and Mem0/OpenMemory are stronger when memory is part of an agent or application architecture. Vestige is MCP- and CLI-accessible local memory for coding agents, with a backward causal-recall path alongside similarity search.
- obsidian-wiki is stronger when several coding agents should read and write the same local compiled knowledge through portable skill instructions.
- Stigmergy exposes the team brain through one MCP server (stdio or streamable HTTP with bearer auth) and through Slack, so questions can be asked without an MCP client; answers cite the pages they used and refuse when a figure cannot be traced.
- Claude Projects/Claude Code is useful when the work already lives inside Claude and project-scoped context is enough.

Choose this path when the missing piece is MCP, API, SDK, plugin, dashboard chat, or platform access that activates memory during work.

## If Memory Needs Governance Or Control

Start with [Membase](../solutions/membase.md), [Hjarni](../solutions/hjarni.md), [GBrain](../solutions/gbrain.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Stigmergy](../solutions/stigmergy.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md), [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md), [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md), [ChatGPT Memory](../solutions/chatgpt-memory.md), or [Claude Projects/Claude Code](../solutions/claude-projects-code.md).

- Membase is useful when you want hosted Memory/Wiki controls and a lower-operations path.
- Hjarni keeps notes, folders, tags, links, and AI instructions directly editable in the app or via MCP, so review, correction, and deletion stay under user control. Storage is hosted-only, with no local option.
- GBrain, obsidian-wiki, Hermes Agent + LLM Wiki, Obsidian/Logseq, and taOSmd are stronger when local files, inspectability, and human review matter more than hosted convenience.
- Stigmergy is the option when the governance question is about a team rather than one person: read permissions are enforced at a single point before retrieval, forbidden and non-existent pages answer identically, an agent's proposed diff has to pass eight deterministic gates before it commits, new entity pages wait for a steward, and answers whose figures cannot be traced to that run's tool results become refusals. It is self-hosted only, at an early release, and you operate the stack.
- Vestige adds explicit memory-governance tools over local SQLite: get/edit, promote/demote, contradiction inspection, reversible active forgetting (`suppress`), and purge of content plus embeddings, with an embedded 3D dashboard for browsing the graph.
- ChatGPT Memory and Claude Projects/Claude Code are useful platform baselines, but visibility, export, and retrieval controls are platform-scoped.

Choose this path when review, correction, deletion, provenance, ownership, permissions, or local/cloud control is the main decision driver.

## If You Already Live In One AI Platform

Start with [ChatGPT Memory](../solutions/chatgpt-memory.md), [Claude Projects/Claude Code](../solutions/claude-projects-code.md), or [NotebookLM](../solutions/notebooklm.md).

These are useful baselines, but they are platform-bound. They should not be treated as a complete self-evolving second brain unless paired with a broader capture, organization, and retrieval layer.

## Assembled Stack vs End-to-End App

If you're deciding between adopting a single product vs combining multiple local tools, see [Assembled Stack vs App](assembled-stack-vs-app.md).
