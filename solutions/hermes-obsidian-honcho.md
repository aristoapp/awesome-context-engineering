# Hermes Agent + Obsidian + Honcho

## Snapshot

- Website / docs: https://hermes-agent.nousresearch.com/
- Company / maintainer: Nous Research (Hermes Agent), Plastic Labs (Honcho), Obsidian MD (Obsidian)
- Status: Active public repos; live personal deployment verified
- Open source: Hermes Agent is open source (Apache 2.0); Honcho is AGPL-3.0; Obsidian is proprietary (local files are open Markdown)
- Deployment: Fully local on user hardware (macOS M1, 16 GB RAM). Hermes Agent runs as a local gateway. Obsidian vault is local Markdown files. Honcho runs as a local FastAPI server with PostgreSQL + pgvector + Redis.
- Primary users: Local-first AI operators who want an inspectable second brain with agent memory, cross-session user modeling, and email integration
- Best second-brain role: Local workspace with integrated agent memory layer
- Last reviewed: 2026-06-10
- Reviewed evidence: Live personal deployment (github.com/SaintChris), Hermes Agent docs, Honcho docs, Obsidian docs, local verification

## One-line Summary

A fully local, multi-layer second brain combining Obsidian as the human-owned knowledge vault, Honcho as the agent memory and user-modeling layer, and Hermes Agent as the runtime that connects them — with AgentMail for email context capture.

## Second-Brain Fit

This is a deliberately assembled local-first stack rather than a single product. Each layer maps to a distinct second-brain lifecycle stage:

- **Collect**: Obsidian vault (manual notes, daily logs, session summaries) + AgentMail (email ingestion into agent inbox) + Hermes skills (web extraction, file processing)
- **Organize**: Obsidian vault structure (entities/, concepts/, comparisons/, shared/) with wiki-links, tags, and YAML frontmatter; Honcho peer cards and conclusions
- **Evolve**: Honcho background reasoning (Deriver worker processes messages, updates peer representations, writes conclusions); Obsidian daily logs and session archives compound over time
- **Use**: Hermes Agent queries Honcho for session context and peer cards; Obsidian vault is searchable via graph, backlinks, and file search; AgentMail triage surfaces actionable emails
- **Govern**: All files are local Markdown (fully inspectable); Honcho provides conclusion inspection and deletion; no cloud dependency

This stack is a good fit when the user wants maximum local ownership, inspectable files, and agent memory that improves over time — and is willing to assemble and maintain the integration.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Fully local. Obsidian vault on local filesystem. Honcho self-hosted (FastAPI + PostgreSQL + pgvector + Redis). Hermes Agent local gateway. No cloud dependency for core functions. |
| Context capture | Built-in + integration. Obsidian: manual notes, daily logs, web clips, file imports. AgentMail: email arrives in agent inbox (hermes876@agentmail.to), triageable by Hermes. Hermes skills: web extraction, PDF parsing, YouTube transcripts, file reading. |
| Knowledge organization | Built-in. Obsidian vault with structured directories (entities/, concepts/, comparisons/, queries/, shared/, raw/), YAML frontmatter, wiki-links, tags, graph view. Honcho: peer cards, conclusions, session context, semantic search. |
| Memory evolution | Built-in (Honcho) + agent-operated (Obsidian). Honcho Deriver worker processes messages asynchronously, updates peer representations, writes conclusions. Obsidian vault grows via daily logs, session summaries, and agent-written pages. |
| Retrieval / use | Hybrid. Obsidian: graph search, backlinks, tags, file search, daily log scroll. Honcho: semantic search, peer card queries, session context injection, dialectic reasoning. Hermes: tool-driven access to both. AgentMail: triage CLI for email. |
| Agent activation / write-back | Built-in. Hermes Agent has native Honcho integration (memory tools injected every prompt). Hermes can read/write Obsidian files via file tools. AgentMail CLI for email send/reply. |
| Personal / team scope | Personal (current). Obsidian vault is single-user. Honcho supports multiple peers (user, AI agents). Team use would require shared vault (git/sync) and Honcho workspace configuration. |
| Feedback / correction | Strong. All Obsidian files are editable Markdown. Honcho conclusions can be inspected and deleted. Mistakes file in vault tracks corrections permanently. |
| Privacy / control | Strong local control. All data stays on local machine. Model API calls go through configured providers (OpenRouter, Ollama), but source data never leaves. |
| Setup / operations | Medium-high. Each component installs independently. Honcho requires PostgreSQL + Redis. Hermes requires Python + gateway. Obsidian is a standard app. Integration is configured via Hermes config.yaml and skills. |

## Strengths

- Fully local, zero cloud dependency for core second-brain functions
- All knowledge is inspectable Markdown — no opaque memory records
- Honcho provides structured agent memory (peer cards, conclusions, semantic search) that improves over time
- AgentMail adds email as a first-class context source
- Hermes Agent connects all layers with a unified tool interface
- Proven in production: 22K+ agent requests, 52 tests, running on $0 cloud cost on M1 Mac
- Mistakes and corrections are permanently logged for continuous improvement

## Limitations

- Not a single product — requires assembling and maintaining 3+ components
- Honcho self-hosting requires PostgreSQL, pgvector, Redis (additional infrastructure)
- No built-in team permissions or shared workspace controls
- Obsidian AI features depend on plugins or external bridges
- AgentMail free plan has inbox limits
- Setup burden is higher than any single end-to-end app

## Best For

- Technical users who want maximum local ownership and inspectability
- AI operators who want agent memory that compounds over time
- People already using Obsidian who want to add agent memory
- Users who want email as a context source in their second brain
- Budget-conscious builders (all components free/OSS, runs on existing hardware)

## Not Ideal For

- Users who want a single-click second-brain product
- Teams needing built-in permissions and governance
- Non-technical users uncomfortable with local server setup
- Workflows requiring broad SaaS connectors without custom integration

## Tradeoffs

This stack trades convenience for control. You get inspectable files, local ownership, and a memory layer that reasons about you over time — but you own the integration, updates, and operational health of three separate systems. It is the local-first, high-autonomy path: maximum ownership, maximum responsibility.

## Official Setup / Evaluation Links

- Hermes Agent: https://hermes-agent.nousresearch.com/
- Hermes Agent GitHub: https://github.com/NousResearch/hermes-agent
- Honcho docs: https://honcho.dev/docs/v3/documentation/introduction/overview
- Honcho GitHub: https://github.com/plastic-labs/honcho
- Obsidian: https://obsidian.md/
- AgentMail: https://agentmail.to/

## Sources

- Live deployment: github.com/SaintChris (portfolio-agentic-infra, hermes-setup-showcase)
- Hermes Agent + Honcho integration: https://honcho.dev/docs/v3/guides/integrations/hermes
- Hermes Agent docs: https://hermes-agent.nousresearch.com/docs
- Honcho docs: https://honcho.dev/docs/v3/documentation/introduction/overview
- Obsidian: https://obsidian.md/help
- AgentMail: https://agentmail.to/
