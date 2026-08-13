# Orbismo

## Snapshot

- Website / docs: https://orbismo.com/ and https://help.orbismo.com/
- Company / maintainer: GhzLab, Inc.
- Status: New, actively developed hosted product. Confirmed as a live Claude connector via hands-on testing for this review, and has a [Claude connector directory listing](https://claude.ai/directory/connectors/orbismo) per the maintainer. Also has a [ChatGPT app listing](https://chatgpt.com/plugins/plugin_asdk_app_6a3afee66ea481919b2a45ae6e623b3a) per the maintainer; both directory pages require a signed-in session to view
- Open source: No, closed-source hosted platform. The companion starter-kit repo, [orbismo-playbook](https://github.com/orbismo/orbismo-playbook), is MIT licensed
- Deployment: Hosted MCP connector, API, and web admin UI
- Primary users: People and small teams who work mainly through Claude or ChatGPT chat and want a shared, structured knowledge graph as their memory layer
- Best second-brain role: Hosted knowledge-graph memory layer, reached primarily through chat via MCP
- Last reviewed: 2026-08-11

## One-line Summary

Orbismo is a hosted, typed knowledge-graph memory layer with a separate addressable layer for rules/conventions and scoped, collaborative worlds, accessed mainly through Claude and ChatGPT chat via MCP.

## Second-Brain Fit

Orbismo fits when the goal is a structured, multi-person knowledge graph that a connected AI reads and writes during normal chat use, not a document store or a flat vector index. Its entity/relationship model and free-text "lore" per entity support genuine Organize and Use coverage, and its `rule` entities give conventions an addressable, trust-stamped home instead of leaving them to a single long prompt. It is a weaker fit for anyone who wants automatic ingestion from common sources or a self-hosted deployment, since capture depends on a connected AI or API calls, and there is no local/self-hosted path.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Hosted only via `app.orbismo.com`; no self-hosted or local deployment option. |
| Context capture | Custom collector: entities, relationships, and lore are written by a connected AI or through the API/MCP write tools. No built-in automatic connectors (email, calendar, Notion, etc.); ingestion patterns for specific workflows are documented as playbooks the user or their agent wires up. |
| Knowledge organization | Built-in typed graph: 9 entity types (person, place, event, group, project, interest, item, reference, rule), 40+ typed relationships, plus a separate layer of semantic predicates (`inspired_by`, `similar_to`, `consequence_of`, etc.), free-text lore per entity, and tags. |
| Memory evolution | Partial. `rule` entities (types include tracker, workflow, guidance, law, canon, policy) are trust-stamped, addressable conventions that a world's base instructions route the agent to, which helps limit drift when many sessions write to the same graph over time. This is explicitly best-effort: a rule does not activate itself, precedence is applied by the agent rather than enforced by Orbismo, and a missed rule is recoverable, not blocked. There is no automatic consolidation, dedup, or dream/decay loop. |
| Retrieval / use | Built-in full-text, tag, and property-predicate entity search; semantic search over lore (embedding-based, returns similarity-ranked chunks, confirmed in hands-on testing); relationship queries; and a timeline query. |
| Agent activation / write-back | Built-in hosted MCP connector (`app.orbismo.com/api/v1/mcp`); confirmed working as a Claude connector via hands-on testing for this review, and has a ChatGPT app listing per the maintainer. Create, update, and delete tools cover entities, relationships, and lore; a `set_active_world`/`list_my_worlds` pair handles switching between worlds inside the same connection. |
| Personal / team scope | Built-in. The "world" is the sharing unit: per-world API keys are scoped read-only or read-write, and a separate per-connected-app grant step controls which of a user's worlds are usable through a given app/connection (confirmed in hands-on testing: a second world was listed but not yet granted to the test connection). |
| Feedback / correction | Partial. The web UI is admin/browsing only; entities are read-only there, so correction goes through a connected AI or the API/MCP write tools. World instructions (the base per-world prompt) are directly editable in the web UI. An `audit_world` tool surfaces data-quality gaps such as property gaps and orphaned entities (confirmed in hands-on testing against a working world) but does not auto-fix them. |
| Privacy / control | Hosted by default; no self-hosted or local path. Access is controlled through per-world API key scope and per-app world grants. Data export/deletion policy: Unknown, not verified from official sources at time of review. |
| Setup / operations | Low to get started: add the connector in Claude or ChatGPT and log in. Medium if authoring a custom world schema, a rule pack, or world instructions for a specific workflow. |

## Strengths

- A genuinely typed graph rather than an embedding store: entities, 40+ relationship types, and a separate semantic-predicate layer, confirmed via a live schema call.
- Rules-as-entities give conventions an addressable, trust-stamped, individually on/off home instead of one long prompt the agent may or may not follow consistently.
- Collaborative by design: worlds support scoped read/write API keys and a separate per-app grant step, not just a single-user memory blob.
- Listed in both the Claude and ChatGPT connector/app directories, so evaluating it does not require installing or hosting anything.
- A public, MIT-licensed starter-kit repo ([orbismo-playbook](https://github.com/orbismo/orbismo-playbook)) ships installable world templates and mini apps, including one named "Second Brain" (verbatim note recall, daily notes, backlinks) directly relevant to this repo's scope.

## Limitations

- No built-in automatic ingestion connectors; getting data in depends on a connected AI or custom integration work.
- No local or self-hosted deployment option.
- Entities cannot be corrected directly in the web UI; correction requires a connected AI or the API.
- Memory evolution is convention-based and agent-followed, not an automatic consolidation or dedup mechanism; official docs state plainly that rules do not activate themselves and a missed rule is recoverable, not blocked.
- New product; less operating history and third-party documentation than more established entries in this repo.

## Best For

- People and small teams who want a shared, structured knowledge graph reachable directly from Claude or ChatGPT chat without standing up infrastructure.
- Workflows that benefit from an explicit, addressable rules/conventions layer; the public orbismo-playbook starter kit covers a personal notebook, reading and movie logs, family history, and travel out of the box, and the same rule/world-instructions mechanism generalizes to other domains.
- Multi-person worlds where collaborators need different (read-only vs. read-write) access to the same graph.

## Not Ideal For

- Users who require local-only or self-hosted storage.
- Teams that need automatic capture from common sources (email, calendar, docs) out of the box.
- Users who want to browse and edit entities directly in a web UI rather than through a connected AI.

## Tradeoffs

Orbismo's bet is a fully typed, addressable graph plus a separate addressable rules layer, reached mainly through chat via MCP rather than through a dedicated app. That buys structure and governance hooks (trust-stamped rules, scoped keys, an audit tool) that looser memory stores do not have, at the cost of automatic ingestion: nothing enters the graph unless a connected AI or an API call puts it there, and there is no local or self-hosted path for anyone who wants to own the infrastructure themselves.

## Official Setup / Evaluation Links

- [Orbismo](https://orbismo.com/)
- [Orbismo help site](https://help.orbismo.com/)
- [Data model reference](https://help.orbismo.com/reference/data-model/)
- [Rules reference](https://help.orbismo.com/reference/rules/)
- [MCP tools reference](https://help.orbismo.com/reference/mcp-tools/)
- [orbismo-playbook starter-kit repo](https://github.com/orbismo/orbismo-playbook)
- [Claude connector directory listing](https://claude.ai/directory/connectors/orbismo) (requires a signed-in Claude session to view)
- [ChatGPT app listing](https://chatgpt.com/plugins/plugin_asdk_app_6a3afee66ea481919b2a45ae6e623b3a) (requires a signed-in ChatGPT session to view)

## Sources

- [Orbismo help site](https://help.orbismo.com/) (data model, rules, MCP tools reference pages)
- [orbismo-playbook repo](https://github.com/orbismo/orbismo-playbook) (README, world-templates, mini-apps)
- Hands-on test against a live Orbismo world via the MCP connector (2026-08-11): schema inspection (`get_world_context`), semantic lore search (`search_lore`), and a world audit (`audit_world`) against a working world with 182 entities across 7 entity types.
- Maintainer-provided Claude connector directory and ChatGPT app listing URLs.
