# Hjarni

## Snapshot

- Website / docs: https://hjarni.com/about
- Company / maintainer: Hjarni
- Status: Active
- Open source: No (app is hosted; the MCP server integration is published under MIT at [hjarni/hjarni-mcp](https://github.com/hjarni/hjarni-mcp))
- Deployment: Hosted SaaS with a remote MCP server at `https://hjarni.com/mcp` (OAuth 2.0)
- Primary users: Individuals and teams who want their AI assistant to read and write their notes
- Best second-brain role: AI-native Markdown notes app with built-in MCP for Claude and ChatGPT
- Last reviewed: 2026-06-10

## One-line Summary

Hjarni is a hosted, AI-native Markdown note-taking app that gives Claude and ChatGPT long-term memory by letting them search, read, create, and organize your notes through a built-in MCP server and REST API.

## Second-Brain Fit

Hjarni is strong for an inspectable, user-authored knowledge base that AI tools can both read and write via MCP. It is not an automatic collector or self-evolving memory layer: context enters through deliberate note-writing rather than background capture, and structure stays under user control.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted SaaS; no self-hosting. The MCP integration is open (MIT), but the app itself is not open source. |
| Context capture | Manual note-writing in Markdown, by the user or by an AI agent through MCP/API. No automatic background collectors. |
| Knowledge organization | Markdown notes in a hierarchy of folders (containers), plus tags and wiki-links for cross-cutting structure. Per-folder and per-team custom AI instructions. |
| Memory evolution | User- and agent-driven edits; no automatic consolidation, deduplication, or refresh loop. |
| Retrieval / use | Search, read, and list notes via MCP tools and REST API. |
| Agent activation / write-back | Built-in MCP server (24+ tools: notes, containers, tags, links, files, instructions, teams, dashboard) for Claude and ChatGPT, plus full REST API. Agents can create and update notes, not just read. |
| Personal / team scope | Personal brains and shared team spaces with member management and team-level instructions. |
| Feedback / correction | Notes, folders, tags, links, and instructions are directly editable in the app or via MCP. |
| Privacy / control | You own the notes and instructions; you bring your own AI provider, so there are no per-message AI costs from Hjarni. Hosted-only storage. |
| Setup / operations | Low. Add Hjarni as a custom connector / MCP server in Claude or ChatGPT (OAuth); no plugins or local setup. |

## Strengths

- Built-in MCP server and REST API make notes directly readable and writable by Claude and ChatGPT.
- Plain Markdown with folders, tags, and wiki-links keeps the brain inspectable and portable in shape.
- Per-folder and per-team AI instructions tailor how agents work with each part of the brain.
- Personal and team spaces in the same product.
- Bring-your-own-AI model avoids per-message token costs from the vendor.

## Limitations

- Capture is manual; there are no automatic connectors or ingestion pipelines.
- No automatic memory evolution (consolidation, dedupe, refresh) — the brain is what you and your agents write.
- Hosted-only; no self-hosted or local deployment.
- Free tier is capped at 25 notes.

## Best For

- People who want a simple Markdown notes app that their AI assistant can actually read and update.
- Claude or ChatGPT users who want MCP-native access to a personal or team knowledge base.
- Teams that want shared notes with per-folder AI instructions.

## Not Ideal For

- Users who need automatic context capture from chats, apps, files, or calendars.
- Workflows that require self-hosting or local-only storage.
- Use cases that depend on automatic memory consolidation or graph-based reasoning.

## Tradeoffs

Hjarni optimizes for a simple, inspectable, agent-readable notes app. The tradeoff is that collection and evolution are manual: it gives AI tools clean read/write access to a knowledge base you author, rather than automatically capturing or consolidating context for you.

## Official Setup / Evaluation Links

- [About Hjarni](https://hjarni.com/about)
- [Hjarni MCP server (setup)](https://github.com/hjarni/hjarni-mcp)
- [Hjarni docs](https://hjarni.com/docs/mcp-vs-custom-gpts)
- [Hjarni FAQ](https://hjarni.com/faq)

## Sources

- [About Hjarni](https://hjarni.com/about)
- [Hjarni MCP server repository](https://github.com/hjarni/hjarni-mcp)
- [Hjarni blog: I gave Claude access to my notes](https://hjarni.com/blog/i-gave-claude-access-to-my-notes)
- [Hjarni FAQ](https://hjarni.com/faq)
