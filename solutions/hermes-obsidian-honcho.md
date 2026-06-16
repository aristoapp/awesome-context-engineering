# Hermes Agent + Obsidian + Honcho

## Snapshot

- Website / docs: https://hermes-agent.nousresearch.com/
- Company / maintainer: Nous Research (Hermes Agent), Plastic Labs (Honcho), Obsidian MD (Obsidian)
- Status: Mixed: Hermes Agent and Honcho have public repos; Obsidian is proprietary
- Open source: Hermes Agent is open source (MIT); Honcho is AGPL-3.0; Obsidian is proprietary (local files are open Markdown)
- Deployment: Multi-component stack. Obsidian vault is local Markdown files. Honcho can be self-hosted (FastAPI + PostgreSQL + pgvector + Redis) or used as a managed service. Hermes Agent runs as a local gateway. AgentMail is a hosted email API.
- Primary users: Local-first AI operators who want an inspectable second brain with agent memory and email integration
- Best second-brain role: Local workspace with integrated agent memory layer
- Last reviewed: 2026-06-10
- Reviewed evidence: Hermes Agent docs, Honcho docs, Obsidian docs, AgentMail docs

## One-line Summary

A multi-component, local-first second brain combining Obsidian as the human-owned knowledge vault, Honcho as the agent memory and user-modeling layer, and Hermes Agent as the runtime that connects them, with AgentMail for email context capture.

## Second-Brain Fit

This is a deliberately assembled stack rather than a single product. Each layer maps to a distinct second-brain lifecycle stage:

- **Collect**: Obsidian vault (manual notes, daily logs, session summaries) + AgentMail (email ingestion into agent inbox) + Hermes skills (web extraction, file processing)
- **Organize**: Obsidian vault structure (entities/, concepts/, comparisons/, shared/) with wiki-links, tags, and YAML frontmatter; Honcho peer cards and conclusions
- **Evolve**: Honcho background reasoning (Deriver worker processes messages, updates peer representations, writes conclusions); Obsidian daily logs and session archives compound over time
- **Use**: Hermes Agent queries Honcho for session context and peer cards; Obsidian vault is searchable via graph, backlinks, and file search; AgentMail triage surfaces actionable emails
- **Govern**: All files are local Markdown (fully inspectable); Honcho provides conclusion inspection and deletion; AgentMail data is managed through AgentMail's service

This stack is a good fit when the user wants local ownership of their knowledge vault and agent memory, inspectable files, and is willing to assemble and maintain the integration.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Multi-component. Obsidian vault on local filesystem. Honcho can be self-hosted (FastAPI + PostgreSQL + pgvector + Redis) or used as a managed service. Hermes Agent local gateway. AgentMail is a hosted email API requiring an account and API key. |
| Context capture | Built-in + integration. Obsidian: manual notes, daily logs, web clips, file imports. AgentMail: email arrives in agent inbox, triageable by Hermes. Hermes skills: web extraction, PDF parsing, YouTube transcripts, file reading. |
| Knowledge organization | Built-in. Obsidian vault with structured directories (entities/, concepts/, comparisons/, queries/, shared/, raw/), YAML frontmatter, wiki-links, tags, graph view. Honcho: peer cards, conclusions, session context, semantic search. |
| Memory evolution | Built-in (Honcho) + agent-operated (Obsidian). Honcho Deriver worker processes messages asynchronously, updates peer representations, writes conclusions. Obsidian vault grows via daily logs, session summaries, and agent-written pages. |
| Retrieval / use | Hybrid. Obsidian: graph search, backlinks, tags, file search, daily log scroll. Honcho: semantic search, peer card queries, session context injection, dialectic reasoning. Hermes: tool-driven access to both. AgentMail: triage via SDK for email. |
| Agent activation / write-back | Built-in. Hermes Agent has native Honcho integration (memory tools injected every prompt). Hermes can read/write Obsidian files via file tools. AgentMail SDK for email send/reply. |
| Personal / team scope | Personal (default). Obsidian vault is single-user. Honcho supports multiple peers (user, AI agents). Team use would require shared vault (git/sync) and Honcho workspace configuration. |
| Feedback / correction | Strong. All Obsidian files are editable Markdown. Honcho conclusions can be inspected and deleted. Mistakes file in vault can track corrections. |
| Privacy / control | Local-first for core components. Obsidian vault and Hermes Agent run on user hardware. Honcho can be self-hosted for full data ownership or used as a managed service. AgentMail processes email on AgentMail infrastructure. Model API calls go through configured providers. |
| Setup / operations | Medium-high. Each component installs independently. Honcho requires PostgreSQL + Redis (self-hosting) or a managed account. Hermes requires Python + gateway. Obsidian is a standard app. AgentMail requires account + API key. Integration is configured via Hermes config.yaml and skills. |

## Strengths

- Obsidian vault is fully inspectable local Markdown, with no opaque memory records for knowledge
- Honcho provides structured agent memory (peer cards, conclusions, semantic search) that improves over time ([Honcho docs](https://honcho.dev/docs/v3/documentation/introduction/overview))
- AgentMail adds email as a first-class context source ([AgentMail docs](https://agentmail.to/))
- Hermes Agent connects all layers with a unified tool interface ([Hermes Agent docs](https://hermes-agent.nousresearch.com/docs))
- Mistakes and corrections can be permanently logged in the vault

## Limitations

- Not a single product; requires assembling and maintaining 3+ components
- Honcho self-hosting requires PostgreSQL, pgvector, Redis (additional infrastructure)
- AgentMail is a hosted service; email data passes through AgentMail infrastructure
- No built-in team permissions or shared workspace controls
- Obsidian AI features depend on plugins or external bridges
- Setup burden is higher than any single end-to-end app

## Best For

- Technical users who want local ownership of their knowledge vault and inspectability
- AI operators who want agent memory that compounds over time
- People already using Obsidian who want to add agent memory
- Users who want email as a context source in their second brain
- Budget-conscious builders (core components are free/OSS; AgentMail has a free tier)

## Not Ideal For

- Users who want a single-click second-brain product
- Teams needing built-in permissions and governance
- Non-technical users uncomfortable with local server setup or multi-component integration
- Workflows requiring broad SaaS connectors without custom integration

## Tradeoffs

This stack trades convenience for control. You get inspectable files, local ownership of your knowledge vault, and a memory layer that reasons about you over time, but you own the integration, updates, and operational health of multiple separate systems. It is a local-first, high-autonomy path: maximum ownership, maximum responsibility.

## Official Setup / Evaluation Links

- Hermes Agent: https://hermes-agent.nousresearch.com/
- Hermes Agent GitHub: https://github.com/NousResearch/hermes-agent
- Honcho docs: https://honcho.dev/docs/v3/documentation/introduction/overview
- Honcho GitHub: https://github.com/plastic-labs/honcho
- Obsidian: https://obsidian.md/
- AgentMail: https://agentmail.to/

## Sources

- Hermes Agent + Honcho integration: https://honcho.dev/docs/v3/guides/integrations/hermes
- Hermes Agent docs: https://hermes-agent.nousresearch.com/docs
- Honcho docs: https://honcho.dev/docs/v3/documentation/introduction/overview
- Obsidian: https://obsidian.md/help
- AgentMail: https://agentmail.to/
