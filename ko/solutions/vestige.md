# Vestige

## 개요

- 웹사이트 / 문서: https://github.com/samvallad33/vestige
- Repository: https://github.com/samvallad33/vestige
- Release: https://github.com/samvallad33/vestige/releases/tag/v2.2.1
- Package: https://www.npmjs.com/package/vestige-mcp-server
- 회사 / 관리자: Sam Valladares (samvallad33), independent
- 상태: Embedded dashboard가 있고 npm과 MCP registry에 배포된 open-source Rust MCP server, tagged release v2.2.1
- 오픈소스: 예, GitHub가 인식한 AGPL-3.0 license repository
- 배포: Local-first. npm package로 설치하는 하나의 prebuilt Rust binary가 local stdio MCP server와 local HTTP/WebSocket dashboard로 동작합니다. Cloud, Docker, API key가 필요 없고 data는 machine에 남습니다.
- 주요 사용자: MCP-compatible coding agent에 local-first이며 확인 가능한 memory를 붙이고 싶은 개발자와 agent 운영자
- 세컨드 브레인 역할: FSRS-6 decay, prediction-error gated write, active forgetting, backward causal-recall path가 있는 local-first agent memory layer
- 마지막 검토: 2026-07-03

## 한 줄 요약

Vestige는 하나의 Rust binary로 배포되어 MCP server로 동작하는 AI agent용 local-first memory layer입니다. Local SQLite와 USearch vector index에 memory를 저장하고, prediction-error 단계가 redundant record를 merge하고 contradictory record를 supersede하며, FSRS-6 spaced-repetition decay로 memory를 aging하고, reversible active forgetting용 `suppress` tool을 제공합니다. Similarity search와 함께 실패의 유사 항목이 아니라 upstream cause를 찾도록 설계된 backward entity-linked recall path인 `backfill`과 검토용 embedded 3D dashboard를 제공합니다.

## 세컨드 브레인 적합도

Vestige는 local에서 실행하면서 memory를 확인 가능하게 유지해야 하는 MCP-compatible agent용 개발자 또는 운영자 관리 memory backend에 가장 잘 맞습니다. 세컨드 브레인에 local SQLite ownership, coding agent MCP access, flat embedding을 계속 쌓기보다 시간에 따라 decay와 consolidation이 일어나는 memory, record를 inspect, correct, suppress, purge하는 명시적 tool이 필요할 때 유용합니다.

이 레포에서는 Mnemosyne, taOSmd, Mem0/OpenMemory, Hindsight, Honcho, Cognee와 가깝습니다. Hosted memory product보다 programmable하고 local-first이지만, built-in OAuth connector, wiki UI, team governance가 있는 end-to-end app보다는 직접 운영할 부분이 많습니다. 주요 차별점은 prediction-error gated write, FSRS-6 decay, consolidation/"dream" maintenance, reversible top-down suppression 같은 cognitive-science-derived lifecycle behavior와 maintainer가 similarity search를 보완한다고 설명하는 backward entity-based recall path입니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | Local-first. 약 23MB의 prebuilt Rust binary를 `vestige-mcp-server` npm package로 설치해 local stdio MCP server로 실행하며 storage는 local SQLite입니다. Cloud, Docker, API key가 필요 없습니다. 첫 실행에서 약 130MB embedding model을 한 번 내려받고 이후 maintainer 설명 기준 fully offline으로 동작합니다. macOS ARM/Intel, Linux x86_64, Windows x86_64 prebuilt binary를 제공합니다. |
| 맥락 수집 | MCP, CLI, agent-driven 방식입니다. `smart_ingest`가 memory를 저장하고, 문서화된 agent-memory protocol은 "remember this", "I prefer", "remind me when" 같은 문구로 save를 trigger합니다. `source_sync`는 외부 source를 local index에 넣으며 GitHub Issues가 문서화되어 있습니다. 넓은 OAuth connector layer가 아니라 agent와 개발자가 capture를 주도합니다. |
| 지식 정리 | Nomic Embed v1.5 embedding을 사용하는 USearch HNSW vector index와 FTS5 full-text search가 있는 local SQLite record입니다. Association과 reasoning chain이 있는 memory graph, synaptic tagging, project별 code memory인 `codebase`가 구조를 더합니다. |
| Memory 발전 | 내장 기능입니다. Prediction-error gating이 redundant write를 merge하고 contradictory memory를 supersede합니다. FSRS-6 decay는 사용된 memory를 유지하고 사용하지 않은 memory를 약화합니다. `maintain` verb는 consolidation, memory 간 link와 synthesis를 만드는 "dream" pass, garbage collection을 실행하고, `dedup`은 duplicate를 탐지하고 merge합니다. |
| 검색 / 활용 | `recall`은 Reciprocal Rank Fusion으로 similarity search, cross-memory reasoning, contradiction detection을 한 호출에 결합합니다. `backfill`은 실패의 upstream cause를 찾기 위한 별도의 backward entity-linked recall path를 제공합니다. MCP, CLI, dashboard에서 context를 retrieve할 수 있고 `intention`은 "X일 때 알려줘" 형태의 prospective trigger를 지원합니다. |
| 에이전트 활용 / 쓰기 반영 | `vestige-mcp` command의 stdio MCP server와 CLI가 내장되어 있습니다. README는 universal MCP config를 통해 Claude Code, Codex, Cursor, Windsurf, VS Code(Copilot), Cline, Continue, Zed, Goose, JetBrains, Xcode, OpenCode, Claude Desktop 설정을 설명합니다. Agent는 memory를 create, edit, promote, demote, suppress, purge할 수 있습니다. |
| 개인 / 팀 범위 | 부분 지원. Project별 code memory와 local scoping으로 context를 분리하지만 team permission이나 shared-workspace product surface는 없고 memory는 한 machine에 local로 존재합니다. |
| 검토 / 정정 | `memory` tool이 record get, edit, promote, demote, purge(content와 embedding)를 제공하고, `suppress`가 reversible top-down forgetting을 적용하며, `contradictions`가 conflicting memory를 보여줍니다. Supersede는 write path에 포함됩니다. |
| 프라이버시 / 통제권 | Local-first입니다. Optional SQLCipher encryption이 있는 local SQLite, one-time model download 이후 cloud call 없음, `maintain`을 통한 export/backup/restore를 제공합니다. Embedding 동작은 local model에 달려 있습니다. |
| 설정 / 운영 | 중간. Npm install 한 번과 MCP config entry로 시작하지만, 실제 가치는 agent-memory protocol wiring, memory-scope 설계, maintenance와 suppression tool 사용 방식에 달려 있습니다. Intel Mac은 repository에 문서화된 Homebrew ONNX Runtime 경로가 필요합니다. |

## 강점

- Npm에서 설치하는 하나의 local Rust binary가 cloud, Docker, API key 없이 local stdio MCP server로 실행되고, optional SQLCipher encryption이 있는 local SQLite에 저장합니다.
- 여러 coding-agent client용 universal config가 문서화되어 있고 agent가 read뿐 아니라 create, edit, promote, demote, suppress, purge할 수 있습니다.
- Prediction-error gating, FSRS-6 decay, consolidation, "dream" synthesis, garbage collection 같은 cognitive-science-derived lifecycle behavior가 내장되어 있습니다.
- `suppress`는 maintainer 설명 기준 penalty를 누적하고 graph neighbor로 확산하며 24시간 안에 되돌릴 수 있는 first-class active-forgetting tool입니다.
- `backfill`은 similarity search와 별도로 failure의 upstream cause를 찾는 backward entity-linked recall path를 제공합니다.
- Get/edit/promote/demote, contradiction inspection, content-plus-embedding purge, export/backup/restore, embedded 3D graph dashboard라는 명시적 governance surface가 있습니다.
- Science doc이 관련 논문과 mechanism을 연결하고, project는 1,550개 test pass와 clippy `-D warnings` clean build를 보고합니다.

## 한계

- 완성형 consumer second-brain app이 아니라 local agent memory backend입니다. 넓은 OAuth app connector, hosted option, team permission은 주 제품 surface가 아닙니다.
- Memory는 한 machine에 local로 존재하고 team permission/shared workspace layer가 없으며 cross-machine portability는 사용자가 export/backup/restore로 운영합니다.
- Maintainer의 causal-recall benchmark는 self-run, maintainer-published measurement이며 재현 전에는 independent third-party evaluation으로 다루면 안 됩니다.
- AGPL-3.0 license가 모든 downstream use에 맞지는 않으므로 제품에 embed하기 전에 license fit을 검토해야 합니다.
- Retrieval, consolidation, suppression 품질은 local embedding model, configuration, memory-scope 설계, agent-memory protocol wiring에 의존합니다.

## 잘 맞는 경우

- Hosted service 없이 Claude Code, Codex, Cursor, Windsurf, VS Code 등에 MCP-accessible local memory를 붙이고 싶은 coding-agent 사용자.
- Flat embedding store 대신 decay, consolidate, dedupe, supersede하는 memory를 원하는 개발자.
- Opaque memory store보다 reversible active forgetting과 content-plus-embedding purge를 포함한 inspection/correction surface를 원하는 사용자.
- Managed memory platform보다 optional SQLCipher가 있는 local SQLite ownership을 선호하는 사용자.

## 잘 맞지 않는 경우

- Hosted dashboard, built-in OAuth connector, 가장 낮은 설정 부담을 원하는 사용자.
- Workspace permission, admin control, governance UI가 즉시 필요한 팀.
- 제한된 notebook이나 wiki로 충분한 source-grounded research workflow.
- AGPL-3.0 license가 blocker인 downstream product.

## 트레이드오프

Vestige는 강한 local control, cognitive-science-derived lifecycle behavior, 명시적 inspection/correction/forgetting surface를 제공하지만 model operation, memory-scope 설계, agent-protocol wiring을 사용자에게 넘기고 hosted/team product가 아닌 single-machine local system입니다. 완성형 hosted second brain보다 local 또는 programmable agent memory가 핵심일 때 Mnemosyne, taOSmd, Mem0/OpenMemory, Hindsight, Honcho, Cognee와 비교하고, built-in decay, consolidation, contradiction handling, reversible forgetting, backward causal-recall path 및 AGPL-3.0 수용 가능성이 중요할 때 우선 검토할 수 있습니다.

## Benchmark

Maintainer는 causal-gap task에서 pure vector retriever가 recall@1 0%, Vestige가 약 60%를 기록했다는 causal-recall benchmark인 CauseBench를 공개합니다. 두 주장을 혼동하면 안 됩니다. 2026 Google DeepMind 결과(arXiv:2508.21038, ICLR 2026)는 single-vector retrieval이 이런 gap을 연결할 수 없다는 theorem으로 인용되고, 0% 대 60% 수치는 maintainer 자체 local measurement입니다. 이 수치는 independent third-party validation이 아닌 maintainer-published self-run measurement로 다루고 의존하기 전에 재현해야 합니다. `backfill`의 "Retroactive Salience Backfill" mechanism은 Zaki/Cai et al. 2024, *Nature* 637:145–155를 port한 것으로 문서화되어 있습니다.

## 공식 설정 / 평가 링크

- Repository: https://github.com/samvallad33/vestige
- Release v2.2.1: https://github.com/samvallad33/vestige/releases/tag/v2.2.1
- npm package: https://www.npmjs.com/package/vestige-mcp-server
- Science doc: https://github.com/samvallad33/vestige/blob/main/docs/SCIENCE.md
- Agent memory protocol: https://github.com/samvallad33/vestige/blob/main/docs/AGENT-MEMORY-PROTOCOL.md
- Claude Code setup: https://github.com/samvallad33/vestige/blob/main/docs/CLAUDE-SETUP.md
- Configuration: https://github.com/samvallad33/vestige/blob/main/docs/CONFIGURATION.md

## 출처

- https://github.com/samvallad33/vestige
- https://github.com/samvallad33/vestige/blob/main/README.md
- https://github.com/samvallad33/vestige/releases/tag/v2.2.1
- https://github.com/samvallad33/vestige/blob/main/docs/SCIENCE.md
- https://www.npmjs.com/package/vestige-mcp-server
