# Deployment / Ownership

## What This Capability Means

Deployment and ownership define where memory lives, who operates storage and indexing, and how much control users have over infrastructure, auth, models, and data residency.

## Evaluation Questions

- Is the system hosted, local, self-hosted, platform-bound, or hybrid?
- Who operates storage, indexes, embeddings, connectors, and MCP/API servers?
- Can teams choose data residency, backups, or self-hosted infrastructure?
- Does the deployment model change sharing, privacy, or setup burden?

## Solution Matrix

| Solution | Support label | Adoption path | Caveats |
|---|---|---|---|
| Membase | Hosted | Account + hosted memory layer and remote MCP. | Fast setup, less infrastructure control. |
| OpenHuman | Hybrid local + managed services | Desktop local state with managed sign-in, model routing, search proxying, and OAuth flows. | Local-first does not mean fully offline by default. |
| GBrain | Local/self-hosted | Local PGLite for personal brains; Postgres/Supabase plus stdio/HTTP MCP for shared, large, or remote deployments. | PGLite is best for single-user local operation; shared/team deployments add database, OAuth, sync, job, and storage operations. |
| Hermes Agent + LLM Wiki | Local/server-owned | Hermes runs on user-controlled infrastructure, and the wiki is a Markdown directory at `WIKI_PATH` or `~/wiki`. | Model providers, web extraction, browser use, and sync choices can still introduce cloud dependencies. |
| Supermemory | Hosted + API | Hosted MCP, API, SDK, and connectors. | Self-hosting/control details should be verified for the target plan. |
| Hyperspell | Hosted + API | Hosted dashboard, memory/context platform, SDKs, API, MCP server, and public plugin/SDK repos. | Core memory platform is managed; private beta availability and data residency/retention details should be verified. |
| Mem0/OpenMemory | Hosted/self-hosted | Hosted Mem0 Platform or open-source server/library path. | Self-hosting still requires memory infrastructure decisions. |
| Zep/Graphiti | Hosted + OSS library | Zep managed platform or Graphiti library integration. | Platform and library are related but not identical surfaces. |
| Cognee | SDK/local/API mode | Python package/SDK with local databases, optional local/Docker MCP setup, or shared API/Cloud mode. | Mode choice affects memory isolation and sharing. |
| Khoj | Cloud/self-hosted | Khoj Cloud or self-hosted personal AI. | Self-hosting requires model/source setup. |
| Obsidian/Logseq + AI bridge | Local-first | Local vault/graph plus optional sync, plugins, or bridges. | Agent memory requires an extra bridge or import path. |
| ChatGPT Memory | Hosted platform | ChatGPT settings and platform memory. | No local or portable deployment for ordinary users. |
| Claude Projects/Claude Code | Hosted platform + local agent | Claude projects plus local Claude Code runtime. | Project knowledge is platform-hosted. |
| NotebookLM | Hosted platform | Google-hosted notebooks and sources. | No local deployment for ordinary users. |

## Sources

- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Hermes Agent website](https://hermes-agent.nousresearch.com/)
- [Hyperspell docs](https://docs.hyperspell.com/)
- [Hyperspell GitHub org](https://github.com/hyperspell)
- [Mem0 open-source overview](https://docs.mem0.ai/open-source/overview)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
