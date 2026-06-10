# Assembled Local Stack vs End-to-End App

## The Core Tradeoff

Most second-brain solutions fall into two adoption patterns:

1. **End-to-end app** — one product that packages collection, organization, retrieval, and UI (e.g., Membase, Khoj, Hjarni)
2. **Assembled local stack** — multiple tools combined, each handling a different lifecycle stage (e.g., Hermes + Obsidian + Honcho)

This page compares these two patterns so readers can decide which adoption model fits.

## Comparison

| Dimension | End-to-end app | Assembled local stack |
|-----------|---------------|----------------------|
| **Setup time** | Minutes (5–30 min) | Hours (~60 min for full stack) |
| **Setup burden** | Low — one account, one config | Medium-high — each component installs and configures independently |
| **Ongoing operations** | Minimal — vendor runs infrastructure | You run servers (PostgreSQL, Redis), updates, backups |
| **Inspectability** | Varies — depends on product UI | High — all data is local files and queryable databases |
| **Portability** | Low — data locked in vendor platform | High — export is copy files / dump database |
| **Customization** | Bounded by product features | High — swap any component, add skills, modify schema |
| **Cost model** | Subscription or usage-based | Free/OSS software; pay only for hardware and model APIs |
| **Failure modes** | Vendor downtime, API changes, pricing changes | Component incompatibility, version drift, operational mistakes |
| **Best for** | Users who want results fast and don't want to operate infrastructure | Users who want maximum control and are willing to maintain the stack |

## When to Choose Each

### Choose an end-to-end app when:
- You want a working second brain in under 30 minutes
- You don't want to run PostgreSQL, Redis, or other services
- You're okay with vendor-managed storage and retrieval
- Your primary need is search/chat over collected sources

### Choose an assembled local stack when:
- You want full ownership of your data
- You need inspectable, editable knowledge (not opaque memory records)
- You're comfortable running local services
- You want to combine best-of-breed tools for each lifecycle stage
- You need the stack to work offline or air-gapped

## Common Assembled Stack Patterns

| Stack | Components | Lifecycle coverage |
|-------|-----------|-------------------|
| **Hermes + Obsidian + Honcho** | Obsidian (vault) + Honcho (memory) + Hermes (runtime) + AgentMail (email) | Collect, Organize, Evolve, Use, Govern |
| **GBrain + Obsidian** | GBrain (brain ops) + Obsidian (notes) | Organize, Evolve, Use, Govern |
| **Mnemosyne + Obsidian** | Mnemosyne (memory) + Obsidian (notes) | Organize, Evolve, Use |
| **Khoj + Obsidian** | Khoj (search/chat) + Obsidian (notes) | Collect, Use |

## Guidance

Start with the lowest-burden option that meets your privacy and portability needs. If an end-to-end app covers your lifecycle gaps, use it. Move to an assembled stack only when you have a specific reason to own storage, indexing, or graph construction — not just because local-first sounds better.

The assembled stack's advantage is control. Its cost is operational responsibility. Be honest about whether you'll actually maintain it.

## Related Pages

- [Local vs Cloud](local-vs-cloud.md) — where memory lives
- [Setup Burden](setup-burden.md) — what you actually operate
- [Solution Layers](solution-layers.md) — app vs workspace vs memory layer
- [Hermes Agent + Obsidian + Honcho](../solutions/hermes-obsidian-honcho.md) — full stack profile
