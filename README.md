<div align="center">

# Awesome AI Second Brain

[![Context Engineering Banner](assets/awesome-second-brain.png)](https://membase.so/?utm_source=github&utm_medium=awesome-second-brain)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

[![Follow on X](https://img.shields.io/badge/Follow%20on%20X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/mem_base)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/aristotechnologies)
[![Join Discord](https://img.shields.io/badge/Join%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/vRp5Zh3HGu)

English | [한국어](README.ko.md)

</div>

> Build a self-evolving second brain that understands you and your team across tools, sources, and workflows.

A curated comparison of second brain, AI memory, and knowledge systems for people who want AI to understand their personal context, team knowledge, and working history. It focuses on the full lifecycle: collecting scattered context, organizing it into durable knowledge, keeping it fresh over time, and making it useful when people or AI tools work.

## Second-Brain Lifecycle

Use this repo to decide how you want your second brain to work end to end:

| Stage | Key question | What to compare |
|---|---|---|
| Collect | How does context from chats, docs, apps, notes, calendars, Slack, email, code, and files enter the brain? | Connectors, imports, APIs, manual notes, custom collectors |
| Organize | Does raw context become structured knowledge instead of a pile of embeddings? | Entities, facts, links, summaries, timelines, tags, Wiki/pages |
| Evolve | Does memory improve as new context arrives and old context gets stale? | Consolidation, deduping, correction, refresh, dream/maintenance loops |
| Use | Can the right context show up when a person or AI tool is doing real work? | Search, grounding, filters, citations, AI-tool access, write-back |
| Govern | Can users and teams inspect, correct, delete, export, scope, and trust the brain? | UI, provenance, activation evidence, permissions, personal/team boundaries, local/cloud control |

## Choose by Starting Point

These entry points are a chooser, not a taxonomy. Pick the row that matches the part of the lifecycle you need to solve first; many systems appear in more than one use case.

| If you want... | Start with | Why |
|---|---|---|
| The fastest end-to-end second brain | [Membase](solutions/membase.md) | Hosted setup for collecting context, organizing it into Memory and Wiki, and making it usable from dashboard chat or AI workflows without running local collectors, graph jobs, or memory infrastructure. |
| Local or self-hosted control | [OpenHuman](solutions/openhuman.md), [GBrain](solutions/gbrain.md), [Hermes Agent + LLM Wiki](solutions/hermes-llm-wiki.md), [Khoj](solutions/khoj.md), or [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md) | Your data can live in local files or self-hosted services, but you own more setup, sync, indexing, and maintenance work. |
| Strong knowledge organization or graph memory | [Membase](solutions/membase.md), [GBrain](solutions/gbrain.md), [Hermes Agent + LLM Wiki](solutions/hermes-llm-wiki.md), [Hyperspell](solutions/hyperspell.md), [Honcho](solutions/honcho.md), [Zep/Graphiti](solutions/zep-graphiti.md), or [Cognee](solutions/cognee.md) | These systems make entities, links, facts, wiki pages, context graphs, graph structure, representations, or temporal memory part of how knowledge is retrieved and maintained. |
| A developer memory API | [Mem0/OpenMemory](solutions/mem0-openmemory.md), [Honcho](solutions/honcho.md), [Hindsight](solutions/hindsight.md), [Supermemory](solutions/supermemory.md), [Hyperspell](solutions/hyperspell.md), [Zep/Graphiti](solutions/zep-graphiti.md), or [Cognee](solutions/cognee.md) | They expose APIs, SDKs, MCP, or managed services for app builders. |
| Bounded source research or platform-native personalization | [NotebookLM](solutions/notebooklm.md), [ChatGPT Memory](solutions/chatgpt-memory.md), or [Claude Projects/Claude Code](solutions/claude-projects-code.md) | Useful when the work lives inside one notebook, source set, or AI platform. |

## Fastest End-to-End Path

[Membase](https://membase.so/?utm_source=github&utm_medium=awesome-second-brain) is the recommended default when your main goal is to get a useful second brain running quickly. It focuses on the whole loop: collect context from AI chats and connected sources, organize it into Memory and Wiki, and make that knowledge available through dashboard chat or connected AI tools.

## Compact Comparison

| Solution | Best second-brain role | Collect | Organize | Evolve | Use | Setup time |
|---|---|---|---|---|---|---|
| [Membase](solutions/membase.md) | Fastest end-to-end hosted second brain | Built-in + Integration | Built-in Memory + Wiki | Built-in | Dashboard chat + MCP/plugin agents | Official: under 5 min |
| [OpenHuman](solutions/openhuman.md) | Local-first personal AI assistant with memory | Built-in + Integration | Built-in Memory Tree + vault | Partial | Desktop agent + connected tools | Official: minutes |
| [GBrain](solutions/gbrain.md) | Local/self-hosted brain operations layer | Built-in + Custom collector | Built-in pages/graph/timeline | Built-in | CLI + stdio/HTTP MCP + skillpack | Official: ~30 min personal |
| [Hermes Agent + LLM Wiki](solutions/hermes-llm-wiki.md) | Agent-operated local Markdown wiki | Built-in source workflow | Built-in Markdown wiki | Partial | Hermes skill/runtime + Markdown wiki | Official quickstart; hands-on varies |
| [Supermemory](solutions/supermemory.md) | Hosted memory API and connector layer | Built-in + Integration | Built-in graph memory | Built-in | MCP + API + SDK + plugins | Official: minutes |
| [Hyperspell](solutions/hyperspell.md) | Hosted company/user context layer for AI agents | Built-in + Integration | Built-in context graph + metadata | Built-in + procedural memory | MCP + API/SDK + agent plugins | Official: under 5 min claim; beta varies |
| [Honcho](solutions/honcho.md) | Stateful agent memory and user-modeling layer | API + Integration | Built-in peer representations + conclusions | Built-in background reasoning | MCP + API/SDK + CLI/plugins | Official quickstart; self-hosting varies |
| [Hindsight](solutions/hindsight.md) | Agent memory API with memory banks | API + Integration | Built-in memory banks + observations | Built-in consolidation | MCP + REST API + SDK + CLI | Official quickstart; hands-on varies |
| [Mem0/OpenMemory](solutions/mem0-openmemory.md) | Developer memory engine | API + Integration | Built-in memory scopes | Partial | MCP + plugins/hooks + CLI + API/SDK | Official: minutes |
| [Zep/Graphiti](solutions/zep-graphiti.md) | Temporal graph memory for apps | API | Built-in temporal graph | Built-in | API + SDK + MCP (read-focused) | Official quickstart; hands-on varies |
| [Cognee](solutions/cognee.md) | Knowledge graph memory SDK with MCP/plugins | Built-in + API/SDK | Built-in knowledge graph | Built-in | Python SDK/Cloud + MCP/API + plugins/CLI | Official: minutes via package install; Docker optional |
| [Khoj](solutions/khoj.md) | Personal AI over files and notes | Built-in | Built-in indexing/search | Partial | Chat/search app + clients + automations | Official: minutes |
| [Obsidian/Logseq + AI bridge](solutions/obsidian-logseq.md) | Human-owned local knowledge base | Built-in notes + Integration | Partial human/PKM structure | Custom collector | Local files + plugin/API/MCP bridge | Hands-on: 30-90 min |
| [ChatGPT Memory](solutions/chatgpt-memory.md) | ChatGPT-native personalization baseline | Built-in | Built-in | Built-in | ChatGPT personalization + sources | Official: instant |
| [Claude Projects/Claude Code](solutions/claude-projects-code.md) | Claude-scoped project knowledge | Built-in | Built-in project knowledge | Built-in RAG for projects | Claude + Claude Code + connectors | Official: minutes |
| [NotebookLM](solutions/notebooklm.md) | Source-grounded research notebook | Built-in | Built-in source summaries | Partial | NotebookLM + Gemini notebook surfaces | Official: minutes |

## Deep Dives

| Page | Use it for |
|---|---|
| [Chooser](comparisons/chooser.md) | Pick a starting solution by goal and tradeoff. |
| [Capability Matrix](comparisons/capability-matrix.md) | Compare support labels, operating burden, and setup time. |
| [Capability Definitions](capabilities/README.md) | Understand the evaluation dimensions behind the matrix. |
| [Activation Evidence](capabilities/activation-evidence.md) | Evaluate whether retrieved memory was loaded, cited, refused, written back, or actually used. |
| [Setup Burden](comparisons/setup-burden.md) | See what you actually have to operate. |
| [Agent Activation](comparisons/agent-access.md) | Compare MCP, API, SDK, CLI, and plugin access as second-brain activation channels. |
| [Local vs Cloud](comparisons/local-vs-cloud.md) | Decide where memory should live. |
| [Personal vs Team](comparisons/personal-vs-team.md) | Compare solo, project, team, and organization fit. |
| [Setup Guides](setup-guides/README.md) | Add hands-on setup notes only after verification. |
| [Examples](examples/README.md) | Describe concrete second-brain workflows and scenarios. |
| [Watchlist](watchlist.md) | Track promising systems that are not yet fully evaluated. |

## Evaluation Labels

| Label | Meaning |
|---|---|
| Built-in | The product directly supports the workflow. |
| Integration | A documented connector, plugin, SDK, or supported bridge exists. |
| Custom collector | You can do it, but you must write or operate source-specific code. |
| Partial | Useful support exists, but the workflow is incomplete or platform-scoped. |
| Not primary fit | The solution is not designed for this workflow. |
| Unknown | The repo has not verified this claim yet. |

Setup time is tagged as `Official`, `Hands-on`, or `Maintainer estimate`. When official docs provide a quickstart but no credible time estimate, the table says that hands-on time varies.

## Sources

Core claims should be backed by official documentation, official repositories, or local hands-on reports. This repo should point to official setup docs instead of duplicating step-by-step installation instructions.

## How To Contribute

1. Pick one solution, capability, comparison, setup guide, example, or watchlist entry.
2. Use [templates/system-profile.md](templates/system-profile.md) or [templates/capability-page.md](templates/capability-page.md).
3. Use primary sources or mark unverified fields as `Unknown`.
4. Link the solution from the relevant capability and comparison pages.
5. Open a PR with sources and verification notes.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the contribution guidelines.

## Star History

<a href="https://www.star-history.com/?repos=aristoapp%2Fawesome-second-brain&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&legend=top-left" />
 </picture>
</a>
