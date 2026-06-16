# Assembled Stack vs End-to-End App

## The Core Tradeoff

Most second-brain solutions fall into two adoption patterns:

1. **End-to-end app**: one product that packages collection, organization, retrieval, and UI (e.g., Membase, Khoj, Hjarni)
2. **Assembled stack**: multiple tools combined, each handling a different lifecycle stage (e.g., Hermes + Obsidian + Honcho)

This page compares these two patterns so readers can decide which adoption model fits. Claims are based on the solution profiles and capability pages linked from each row.

## Comparison

| Dimension | End-to-end app | Assembled stack |
|-----------|---------------|-----------------|
| **Setup time** | Minutes (5-30 min) | Varies by number of components; multi-component stacks can take 60+ min |
| **Setup burden** | Low: one account, one config | Medium-high: each component installs and configures independently |
| **Ongoing operations** | Minimal: vendor runs infrastructure | Varies: self-hosted components (PostgreSQL, Redis) require server management; managed services reduce this burden |
| **Inspectability** | Varies by product UI | Varies by component: locally-run components (Obsidian vault, Honcho DB) are inspectable; hosted-service components depend on that service's audit surfaces |
| **Portability** | Varies by export options | Varies by component: file-based components (Obsidian) are portable; hosted-service components depend on that service's export capabilities |
| **Customization** | Bounded by product features | High: swap any component, add skills, modify schema |
| **Cost model** | Subscription or usage-based | Varies by component: local/OSS components (Obsidian, Honcho self-hosted, Hermes) are free; hosted services (AgentMail, Honcho managed) have separate pricing |
| **Failure modes** | Vendor downtime, API changes, pricing changes | Component incompatibility, version drift, operational mistakes |
| **Best for** | Users who want results fast and don't want to operate infrastructure | Users who want maximum control and are willing to maintain the stack |

## When to Choose Each

### Choose an end-to-end app when:

- You want a working second brain in under 30 minutes
- You don't want to run PostgreSQL, Redis, or other services
- You're okay with vendor-managed storage and retrieval
- Your primary need is search/chat over collected sources

### Choose an assembled stack when:

- You want full ownership of your data (for locally-run components)
- You need inspectable, editable knowledge (not opaque memory records)
- You're comfortable running local services
- You want to combine best-of-breed tools for each lifecycle stage
- You need locally-run components to work offline (note: hosted services like AgentMail still require internet)

## Common Assembled Stack Patterns

| Stack | Components | Lifecycle coverage | Notes |
|-------|-----------|-------------------|-------|
| **Hermes + Obsidian + Honcho** | Obsidian (vault) + Honcho (memory) + Hermes (runtime) + AgentMail (email) | Collect, Organize, Evolve, Use, Govern | AgentMail is a hosted email API; Honcho can be self-hosted or managed. See [solution profile](../solutions/hermes-obsidian-honcho.md). |
| **GBrain + Obsidian** | GBrain (brain ops) + Obsidian (notes) | Organize, Evolve, Use, Govern | See [GBrain profile](../solutions/gbrain.md). |
| **Mnemosyne + Obsidian** | Mnemosyne (memory) + Obsidian (notes) | Organize, Evolve, Use | See [Mnemosyne profile](../solutions/mnemosyne.md). |
| **Khoj + Obsidian** | Khoj (search/chat) + Obsidian (notes) | Collect, Use | See [Khoj profile](../solutions/khoj.md). |

## Guidance

Start with the lowest-burden option that meets your privacy and portability needs. If an end-to-end app covers your lifecycle gaps, use it. Move to an assembled stack only when you have a specific reason to own storage, indexing, or graph construction, not just because local-first sounds better.

The assembled stack's advantage is control. Its cost is operational responsibility. Be honest about whether you'll actually maintain it.

## Related Pages

- [Local vs Cloud](local-vs-cloud.md): where memory lives
- [Setup Burden](setup-burden.md): what you actually operate
- [Solution Layers](solution-layers.md): app vs workspace vs memory layer
- [Hermes Agent + Obsidian + Honcho](../solutions/hermes-obsidian-honcho.md): full stack profile
