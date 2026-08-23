# Persona

## Snapshot

- Website / repo: https://github.com/jayamitkatariya/personacli
- Company / maintainer: jayamitkatariya
- Status: Active public repo (v0.2.0)
- Open source: Yes (MIT)
- Deployment: Local macOS app; plain Markdown files on disk, no cloud or database required
- Primary users: Individual knowledge workers who want notes, tasks, and AI chat in one local workspace
- Best second-brain role: Local-first collect/organize/use workspace with grounded AI chat
- Last reviewed: 2026-08-23
- Reviewed evidence: official repo README, v0.2.0 release notes, and repository source

## One-line Summary

Persona is a local-first personal workspace where notes and tasks live as plain Markdown on your machine and an AI chat answers questions grounded in those same files.

## Second-Brain Fit

Persona covers the Collect → Organize → Use segments of the lifecycle. Everything is stored as portable `.md` files (no vendor lock-in), and the chat layer cites the user's actual notes and tasks rather than answering from thin air. It runs against Ollama or any OpenAI-compatible endpoint, so it can operate fully offline.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Fully local; `persona` boots a local server and opens the browser. No accounts. |
| Context capture | Markdown note writing/editing, task capture with project tags, note importers from other tools. |
| Knowledge organization | Plain Markdown files; any editor or agent can read them directly. |
| Retrieval / use | Chat grounded in workspace files with cited sources; date-aware context. |
| Agent activation | Background agents for longer jobs outside the chat thread (v0.2.0). |
| Privacy / control | Strong — data never leaves the machine when using local models via Ollama. |
| Setup / operations | Low: Node 20+, one command to run. |

## Strengths

- True local-first: if Persona disappeared tomorrow, the second brain is still a folder of `.md` files.
- Grounded chat reduces hallucination by citing your own notes.
- Works fully offline with Ollama.

## Tradeoffs

- macOS-only today (Apple Silicon recommended); Windows/Linux not yet supported.

## Links

- Repository: https://github.com/jayamitkatariya/personacli
- License: MIT
