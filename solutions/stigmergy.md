# Stigmergy

## Snapshot

- Website / docs: https://github.com/sturlese/stigmergy (repository README and `docs/`; no separate product site)
- Company / maintainer: sturlese (independent maintainer)
- Status: Public repo; first tagged release `v0.1.0` (2026-08-07). Pre-1.0: the maintainer states that documented contracts may move between minor releases while behavior changes require a decision record.
- Open source: Yes (Apache-2.0)
- Deployment: Self-hosted only. A Python service (Docker image and `fly.toml` provided) plus Postgres + pgvector, an S3-compatible object store, and a separate git repository that holds the knowledge. No hosted option.
- Primary users: Small teams and operators who want a shared knowledge base with permission-scoped reads, agent-written pages, and a human approval step for new entities
- Best second-brain role: Self-hosted team brain with gated writes and cited-or-refused reads
- Last reviewed: 2026-08-09
- Reviewed evidence: official repository README, `docs/reference/` (server, librarian, capture, slack, gardener-digest, knowledge-repo, operator-runbook, admin-console), `docs/decisions/`, `CHANGELOG.md`, and the `v0.1.0` release

## One-line Summary

Stigmergy is a self-hosted team second brain: captures arrive from Slack, MCP, or operator CLIs, an agent files them as Markdown pages into a git repository the team owns, deterministic gates decide what is allowed to commit, and a single MCP server answers questions with citations or refuses.

## Second-Brain Fit

Stigmergy is adopted as a deployed service, not as a folder someone edits. The team's activation surfaces are Slack and MCP clients; the git repository underneath is the storage substrate and the exit path, not the working surface. Nobody is expected to hand-maintain the pages, and the design actively discourages it: an entity page is created only after a steward approves the proposal, and the agent's diff has to pass eight deterministic checks before it can land.

That places it in the end-to-end app layer rather than the local-workspace layer, with two differences from the hosted apps in that group: the deployment is yours to run, and the governance surface (audience scopes, approval queue, gates, refusal behavior) is the part the project invests in most.

It is a fit when a team wants shared knowledge with read permissions and an audit trail over its own infrastructure. It is not a personal note-taking app, not a connector marketplace, and not a memory API for building products on.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment / ownership | Self-hosted. The service runs on infrastructure you operate; pages live in a separate git repository you control, and the Postgres index is described as a rebuildable cache (`stigmergy-index --rebuild`). No hosted or managed option exists. |
| Context capture | Built-in through Slack (an emoji reaction captures a message verbatim in public channels), the `brain_submit` MCP tool, and an operator CLI that drops meeting transcripts. There is no platform-level connector catalog; other sources need custom submission. |
| Knowledge organization | Built-in. A filing agent writes Markdown pages under a documented page contract and repo layout, with frontmatter, an entity registry, resolved links and backlinks, and per-entity rollup views. A dropped meeting transcript becomes a source page, a meeting page, and one page per decision. New entity names are not invented: the agent asks once, parks the capture, and waits for a steward. |
| Memory evolution | Partial. Later captures are folded into the pages they touch, pages carry `status`/`supersedes`/`superseded_by`, and a "gardener" job runs eight deterministic corpus-health checks plus a bounded model review. The gardener reports findings and applies no fixes by design, so acting on them is operator work. Capture payloads are purged on a 30-day retention window. |
| Retrieval / use | Built-in. Hybrid Postgres full-text plus pgvector retrieval combined with reciprocal rank fusion, exposed through five read tools (`search_brain`, `read_page`, `list_entities`, `describe_entity`, `ask`) and a CLI. `ask` runs an evidence-gathering agent, then a deterministic verifier that traces every figure and citation back to what the tools returned in that run; anything untraceable becomes a stated refusal. |
| Agent activation / write-back | Built-in. Ten MCP tools over stdio or streamable HTTP with per-request bearer-token auth, covering read, capture/write, and review. Write-back is mediated: an agent submits a capture, and the filing worker plus the gates decide what commits. Clients cannot write pages directly. |
| Personal / team scope | Built-in. Identities map to audience scopes in a versioned `ops/identities.json`; `acl.visible()` is the single enforcement point on every read surface, checked before retrieval, and an unknown page and a forbidden page return the same response so existence is not leaked. In Slack a DM answers under the caller's scope and a public mention under the channel's. There is no SSO or directory sync. |
| Feedback / correction | Built-in. A review inbox in Slack and through the `review_queue`/`review_decide` MCP tools handles entity proposals and parked captures; a `stigmergy-queue` CLI lists, requeues, resolves, rejects, and purges. Pages are Markdown in git, so correction and history are ordinary repository operations. A web `/admin` console covers operations only and is barred from reading pages. |
| Privacy / control | Self-hosted with the knowledge in your own repository, exportable by definition since it is Markdown in git. Secrets and PII gates run over each proposed diff, a capture rejected for a secret or PII match has its payload purged immediately regardless of age, and raw source bytes are kept content-addressed in the object store so a claim can be traced back. Model calls go to whichever provider you configure. |
| Setup / operations | High. Python 3.12+, Docker, Postgres + pgvector, an S3-compatible object store, a git knowledge repository, provider API keys, and a Slack app for the team surfaces; an operator runbook covers deploys, three scheduled jobs, token rotation, backup/restore drills, and index rebuilds. |

## Strengths

- Knowledge is Markdown in a git repository the team owns, with history, and the maintainer states the index can be rebuilt from it.
- Writes pass eight deterministic gates (zone, binary-page, body-rewrite, secrets, PII, frontmatter, contract, anchoring) over the proposed diff rather than relying on model judgment.
- New entity pages require a human approval step, which addresses the duplicate-entity problem that appears when several writers share one wiki.
- Read permissions are enforced at one point before retrieval, with an architecture test that fails the build when a module reads the page index without either naming an ACL predicate or sitting on a declared exception list, and forbidden and non-existent pages are answered identically.
- Answers are verified after generation: figures that cannot be traced to what the tools returned in that run are withheld and the response becomes a refusal.
- Capture, review, and answering are reachable from Slack, so the team surface does not require an MCP client.
- The repository ships golden retrieval and golden QA evals over a frozen corpus, an operator runbook, architecture decision records, and end-to-end proofs that run offline against deterministic fake model backends.

## Limitations

- Early project: first public release `v0.1.0` on 2026-08-07, one maintainer, and no independent third-party validation. The published evals are maintainer-produced.
- Self-hosted only. There is no hosted or trial path, so evaluating it means standing up Postgres + pgvector, an object store, a git knowledge repo, and a Slack app.
- Identity is configuration, not authentication: `ops/identities.json` maps emails to audience scopes, and the maintainer documents that anyone who can edit it, or pass `--identity` over stdio, can impersonate at the scope layer. HTTP callers additionally need a bearer token. Google Workspace OAuth is described as not built.
- No platform-level connectors. The documented sources are Slack, MCP `brain_submit`, and operator CLIs; anything else is custom work. Where a file store is involved the fetch is deliberately client-side: a Google Drive file, for example, enters through a command an operator runs on their own machine with their own Google credential, and the maintainer states that no Google credential exists server-side. That is a documented design decision rather than a gap, but it means the deployed service holds no connector to keep a source in sync.
- Consolidation is reported, not applied: the gardener writes findings and fixes nothing, so corpus hygiene stays operator-driven.
- No reading UI for knowledge. Navigation is served through MCP tools and Slack; the `/admin` console is for operations and never reads pages. Its activity tab does expose the questions people asked, behind one shared credential.
- One knowledge repository by design, with no per-team enclaves, so separation relies on audience labels rather than separate stores.
- Pre-1.0: documented contracts may change between minor releases.

## Best For

- Small teams that want shared knowledge on infrastructure they control, with read scopes and an audit trail.
- Organizations where an incorrect or over-shared page is a real cost and a human approval step for new entities is worth the friction.
- Teams that already work in Slack and want capture and questions to happen there rather than in a separate app.
- Operators comfortable running Postgres, an object store, and a scheduled-job deployment.

## Not Ideal For

- Individuals looking for a personal note-taking app or a local vault they edit by hand.
- Teams that want a hosted product with OAuth connectors and no infrastructure to run.
- Developers looking for a memory API or SDK to embed in their own product.
- Anyone who needs SSO, directory-based identity, or per-team isolated stores today.
- Buyers who require a mature release history or independent validation before adoption.

## Tradeoffs

Stigmergy trades setup and operational burden for ownership and control over what enters shared knowledge and who can read it. The governance surface is unusually explicit for a project at this stage, but it is also the project's own early implementation, and both the deployment and the corpus hygiene remain the team's work. Compared with the hosted end-to-end apps in this repo, the cost is time-to-first-value; compared with the local workspaces, the difference is that a team, not a person, is the unit of adoption.

## Official Setup / Evaluation Links

- [Stigmergy repository and README](https://github.com/sturlese/stigmergy)
- [Operator runbook](https://github.com/sturlese/stigmergy/blob/main/docs/reference/operator-runbook.md)
- [Knowledge repo contract](https://github.com/sturlese/stigmergy/blob/main/docs/reference/knowledge-repo.md)
- [MCP server reference (tools, transports, ACL semantics)](https://github.com/sturlese/stigmergy/blob/main/docs/reference/server.md)
- [Evals: golden retrieval and golden QA](https://github.com/sturlese/stigmergy/tree/main/evals)

## Sources

- [Stigmergy repository](https://github.com/sturlese/stigmergy)
- [README](https://github.com/sturlese/stigmergy/blob/main/README.md)
- [CHANGELOG and `v0.1.0` release](https://github.com/sturlese/stigmergy/releases/tag/v0.1.0)
- [LICENSE (Apache-2.0)](https://github.com/sturlese/stigmergy/blob/main/LICENSE)
- [`docs/reference/server.md`](https://github.com/sturlese/stigmergy/blob/main/docs/reference/server.md)
- [`docs/reference/librarian.md`](https://github.com/sturlese/stigmergy/blob/main/docs/reference/librarian.md)
- [`docs/reference/capture.md`](https://github.com/sturlese/stigmergy/blob/main/docs/reference/capture.md)
- [`docs/reference/slack.md`](https://github.com/sturlese/stigmergy/blob/main/docs/reference/slack.md)
- [`docs/reference/gardener-digest.md`](https://github.com/sturlese/stigmergy/blob/main/docs/reference/gardener-digest.md)
- [`docs/reference/admin-console.md`](https://github.com/sturlese/stigmergy/blob/main/docs/reference/admin-console.md)
- [`docs/reference/operator-runbook.md`](https://github.com/sturlese/stigmergy/blob/main/docs/reference/operator-runbook.md)
- [`docs/decisions/`](https://github.com/sturlese/stigmergy/tree/main/docs/decisions)
