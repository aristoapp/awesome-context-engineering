# Cognee

## Snapshot

- Website / docs: https://docs.cognee.ai/
- Company / maintainer: Cognee
- Status: Active memory and knowledge graph platform
- Open source: Open-source core with cloud/API options
- Deployment: Python package/SDK, local or Docker MCP server, Cognee Cloud/API mode
- Primary users: Developers and AI power users who want knowledge graph memory through SDK, MCP, or agent plugins
- Best second-brain role: Knowledge graph memory SDK with MCP/plugin access
- Last reviewed: 2026-05-31

## One-line Summary

Cognee exposes persistent knowledge graph memory through a Python SDK, API/Cloud options, MCP, and agent integrations.

## Second-Brain Fit

Cognee is a strong option when the user wants persistent AI memory and graph construction from code, MCP-compatible clients, or agent plugins. It sits between local/self-hosted control and hosted second-brain platforms.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Python package/SDK with default local databases, local or Docker MCP server, or API/Cloud mode connected to a centralized backend. Docker is optional, not required. |
| Context capture | SDK/API flows, MCP tools, data operations, and memory operations. |
| Knowledge organization | Built-in knowledge graph construction and memory tools. |
| Memory evolution | Built-in improve/processing workflows, but terminology differs from "dreaming." |
| Retrieval / use | Knowledge graph memory with `remember`, `recall`, `forget_memory`, and `improve` tools. |
| Agent activation / write-back | SDK/API plus MCP and plugin/client integrations; documented surfaces include Claude Code, Cursor, Codex, Continue, Cline, Roo Code, Goose, OpenClaw, and Python agents. |
| Personal / team scope | Standalone mode isolates memory; API mode supports shared graph use across clients. |
| Feedback / correction | Developer/admin surfaces and tool references; end-user UI should be verified for the target workflow. |
| Privacy / control | Local mode gives more control; API mode centralizes sharing. |
| Setup / operations | Medium. Package install is the lightweight path; Docker and API/Cloud modes are optional deployment choices. Graph memory design still matters. |

## Strengths

- SDK-first memory API with MCP and agent integration paths.
- Clear standalone vs API mode distinction.
- Useful for codebase and project memory across compatible AI tools.

## Limitations

- Mode choice can fragment memory if each client runs its own standalone instance.
- More developer-oriented than consumer-oriented.
- Team and governance details depend on API/cloud setup.

## Best For

- Developers who want MCP-accessible knowledge graph memory.
- Users who need SDK, local MCP, optional Docker, or shared API/Cloud deployment choices.
- Codebase and project memory across compatible agent clients.

## Not Ideal For

- Nontechnical users who want the lowest setup burden.
- Workflows that need a polished consumer second-brain UI first.
- Teams that do not want to choose and operate a memory deployment mode.

## Tradeoffs

Cognee gives users more deployment choice than platform-bound memory features, especially through SDK/local, MCP, Docker, and API/Cloud modes. The tradeoff is that teams must choose the right mode carefully; otherwise, each client can end up with isolated memory instead of one shared knowledge graph.

## Official Setup / Evaluation Links

- [Cognee installation](https://docs.cognee.ai/getting-started/installation)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [Cognee client integrations](https://docs.cognee.ai/cognee-mcp/integrations)
- [Cognee GitHub repository](https://github.com/topoteretes/cognee)

## Sources

- [Cognee installation](https://docs.cognee.ai/getting-started/installation)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [Cognee client integrations](https://docs.cognee.ai/cognee-mcp/integrations)
- [Cognee GitHub repository](https://github.com/topoteretes/cognee)
