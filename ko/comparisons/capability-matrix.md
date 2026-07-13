# 기능 매트릭스

행은 주 계층별로 묶었고, 열은 생애주기, 활용 증거, 거버넌스 지원 범위를 비교합니다. 계층 정의는 [Solution Layers](solution-layers.md)를 참고하세요.

## End-To-End Apps

| 솔루션 | 맥락 수집 | 지식 정리 | Memory 발전 | 검색/활용 | 활용 증거 | 검토/정정 | 개인/팀 범위 | 프라이버시/통제권 | 에이전트 활용 | 설정/운영 | 설정 시간 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [Membase](../solutions/membase.md) | 내장 + 연동 | 내장 Memory + Wiki | 내장 | Memory용 graph + vector hybrid RAG, Wiki용 vector + keyword hybrid search, 대시보드 채팅 | 부분 지원: retrieval과 연결된 AI workflow surface가 있지만 workflow별 retrieved-vs-used evidence 확인이 필요합니다. | 내장 대시보드 제어 | 부분 지원: project/collection 범위 지정, team/workspace 분리는 출시 예정 | 호스팅형 제어 | MCP + 플러그인 + 대시보드 채팅 | 낮음 | 공식: 5분 이내 |
| [OpenHuman](../solutions/openhuman.md) | 내장 + 연동 | 내장 Memory Tree + Markdown vault | 부분 지원 | 로컬 Memory Tree + vault + memory graph | 부분 지원: local state와 vault는 inspectable하지만 acted-on proof는 assistant/tool log에 달려 있습니다. | 내장 데스크톱 화면 | 주 용도 아님 | 로컬 memory + 관리형 서비스 | 데스크톱 agent + skill/tool + 선택적 agentmemory backend | 낮음-중간 | 공식: 몇 분 |
| [Khoj](../solutions/khoj.md) | 내장 | 내장 인덱싱/검색 | 부분 지원 | 파일, 노트, 문서, 웹 위의 채팅과 자연어 검색 | 부분 지원: source-backed chat/search가 input을 보여줄 수 있지만 retrieved-vs-acted-on evidence는 client log에 달려 있습니다. | 내장 앱/클라이언트 UI | 부분 지원 | Cloud 또는 self-hosted | Web/app client + 내장 agent/automation | 중간 | 공식: 몇 분 |

## Local Workspaces

| 솔루션 | 맥락 수집 | 지식 정리 | Memory 발전 | 검색/활용 | 활용 증거 | 검토/정정 | 개인/팀 범위 | 프라이버시/통제권 | 에이전트 활용 | 설정/운영 | 설정 시간 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [GBrain](../solutions/gbrain.md) | 내장 + 커스텀 수집기 | 내장 page/graph/timeline/schema | 내장 | 저비용 hybrid search + 확장 query + `think` 종합 | 부분 지원: citation, conflict, gap analysis가 activation check를 도울 수 있지만 acted-on proof는 workflow 검증이 필요합니다. | 부분 운영/관리 UI | 내장, 단 운영 필요 | 로컬/self-hosted 통제 | CLI + stdio/HTTP MCP + agent skillpack | 중간-높음 | 공식: 개인용 약 30분 |
| [obsidian-wiki](../solutions/obsidian-wiki.md) | 내장 skill workflow + local source | 내장 Markdown page/frontmatter/wikilink/index/manifest | 내장, 단 agent가 운영 | metadata + graph candidate ranking, 선택적 page read, linked answer | 부분 지원: source frontmatter, page link, log, local file은 inspectable하지만 acted-on proof는 agent log에 달려 있습니다. | 내장 Markdown review + lint/dedup/rebuild workflow | 부분 지원: named vault/project scope, team control은 외부 | local vault ownership, provider/sync 선택은 외부 | portable agent skill + local CLI, 전용 MCP/API 없음 | 중간 | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | 내장 | 내장 Markdown wiki/schema/index/log | 부분 지원 | wiki orientation + Markdown file search + page synthesis | 연동: local wiki file이 source audit을 쉽게 만들지만 활용 증거는 skill behavior에 달려 있습니다. | 내장 Markdown 검토 + lint workflow | 부분 지원 | 로컬/사용자 서버 파일 | Hermes 번들 skill/runtime | 중간 | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | 내장 노트 + 연동 | 사람이 관리하는 PKM 구조에 부분 의존 | 커스텀 수집기 | 로컬 search/graph + plugin RAG | 연동: local note, backlink, file history는 auditable하지만 bridge가 loaded/used context를 기록해야 합니다. | 내장 사람 검토 UI | 부분 지원 | 로컬 vault/graph 통제 | 로컬 파일 + plugin/API/MCP bridge | 중간-높음 | 직접 설정: 30-90분 |

## Agent Memory Layers

| 솔루션 | 맥락 수집 | 지식 정리 | Memory 발전 | 검색/활용 | 활용 증거 | 검토/정정 | 개인/팀 범위 | 프라이버시/통제권 | 에이전트 활용 | 설정/운영 | 설정 시간 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [Supermemory](../solutions/supermemory.md) | 내장 + 연동 | 내장 graph memory | 내장 | Memory API + hybrid search + graph memory | 부분 지원: MCP/API retrieval이 trace에 들어갈 수 있지만 app owner가 어떤 context가 사용됐는지 기록해야 합니다. | 내장 hosted app/console | 연동 | 호스팅형 제어 | MCP + API + SDK + plugin | 낮음-중간 | 공식: 몇 분 |
| [Hyperspell](../solutions/hyperspell.md) | 내장 + 연동 | 내장 context graph + metadata | 내장 + procedural memory | indexed/live search + grounded answer + API action | 부분 지원: MCP search/get과 metadata filter가 activated input을 보여줄 수 있지만 host usage log 검증이 필요합니다. | API review flow + app-owned UI | 내장 user model | 호스팅형 제어 | MCP + API/SDK + agent plugin | 낮음-중간 | 공식: 5분 이내 주장, beta 여부에 따라 달라짐 |
| [Honcho](../solutions/honcho.md) | API + 연동 | 내장 peer representation + conclusion | 내장 background reasoning | Search + context + representation | 부분 지원: session/peer context API가 available context를 설명할 수 있지만 acted-on evidence는 app level입니다. | 부분 개발자/API 도구 | 내장 peer/workspace model | Hosted 또는 self-hosted | MCP + API/SDK + CLI/client plugin | 중간 | 공식 quickstart 있음, self-hosting은 달라짐 |
| [Hindsight](../solutions/hindsight.md) | API + 연동 | 내장 memory bank + observation | 내장 consolidation | semantic/keyword/graph/temporal recall + reflect | 부분 지원: memory-bank retrieval과 observation이 trace를 도울 수 있지만 retrieval과 action을 workflow에서 연결해야 합니다. | 부분 개발자/API 도구 | 부분 memory-bank scoping | Cloud, Docker, package, embedded server, local MCP | MCP + REST API + SDK + CLI | 중간 | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Mnemosyne](../solutions/mnemosyne.md) | API + 연동 | 내장 memory tier + TripleStore | 내장 consolidation | vector + FTS5 + importance hybrid recall | 부분 지원: MCP/Hermes tool call은 retrieval을 보여줄 수 있지만 acted-on proof는 agent log에 달려 있습니다. | 부분 개발자/운영자 도구 | 부분 memory-bank scoping | local SQLite | MCP + Python SDK + CLI + Hermes plugin | 중간 | 공식: 몇 분, 운영 부담은 달라짐 |
| [taOSmd](../solutions/taosmd.md) | API + 연동 | 내장 archive + knowledge graph + librarian | 내장 supersede + retention | Hybrid keyword + vector + fusion, optional rerank, knowledge graph | 부분 지원: append-only archive, pending-review list, local dashboard가 input을 inspectable하게 만들지만 acted-on proof는 agent log에 달려 있습니다. | graph/vector 양쪽의 supersede, raw archive 보존, pending-review surface | 부분 per-agent shelf + cross-agent read, team permission 제품은 아님 | Local-first, offline, cloud 없음; local SQLite와 ONNX embedding | MCP + HTTP/REST + Python API + CLI + dashboard, optional remote client | 중간 | 직접 설정: source install 몇 분 + local model download |
| [Vestige](../solutions/vestige.md) | MCP + 연동 | 내장 SQLite + FTS5 + USearch vector index + memory graph | 내장 prediction-error gating + FSRS-6 decay + consolidation/dream + dedup | RRF hybrid recall과 별도의 backward entity-linked causal-recall 경로 | 부분 지원: MCP tool call과 local 3D dashboard가 input을 inspectable하게 만들지만 acted-on proof는 agent log에 달려 있습니다. | 내장 get/edit/promote/demote, supersede, contradiction inspection, reversible suppress, content+embedding purge | 부분 지원: per-project code memory와 local scoping, team permission 제품은 아님 | Local-first, one-time model download 이후 cloud 없음; local SQLite, optional SQLCipher | MCP(stdio) + CLI + dashboard | 중간 | 공식: 설치 몇 분 + 약 130MB model one-time download |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | API + 연동 | 내장 memory 범위 | 부분 지원 | Layered memory search + auto context injection | 부분 지원: user/run-scoped memory search가 activation trace를 도울 수 있지만 acted-on proof는 app level입니다. | 내장 dashboard/server 경로 | 내장 | Hosted 또는 self-hosted | MCP + plugin/hook + CLI + API/SDK | 중간 | 공식: 몇 분 |

## Memory Substrates

| 솔루션 | 맥락 수집 | 지식 정리 | Memory 발전 | 검색/활용 | 활용 증거 | 검토/정정 | 개인/팀 범위 | 프라이버시/통제권 | 에이전트 활용 | 설정/운영 | 설정 시간 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [Zep/Graphiti](../solutions/zep-graphiti.md) | API | 내장 temporal graph | 내장 | Temporal knowledge graph + Graph RAG | 부분 지원: temporal graph fact와 episode가 evidence input을 제공하지만 application이 usage log를 남겨야 합니다. | 부분 개발자 UI/API | 내장 | Hosted 또는 OSS library 경로 | API + SDK + MCP(읽기 중심) | 중간 | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Cognee](../solutions/cognee.md) | 내장 + API/SDK | 내장 knowledge graph | 내장 | Knowledge graph memory | 부분 지원: recall tool이 structured context를 반환하지만 workflow별 usage evidence 검증이 필요합니다. | 부분 개발자/관리자 화면 | API 모드에서 내장 | SDK/local mode, 선택적 Docker, self-hosted API 또는 Cloud SDK | Python SDK/Cloud + MCP/API + plugin/CLI | 중간 | 공식: package install 기준 몇 분, Docker는 선택 사항 |

## Platform Baselines

| 솔루션 | 맥락 수집 | 지식 정리 | Memory 발전 | 검색/활용 | 활용 증거 | 검토/정정 | 개인/팀 범위 | 프라이버시/통제권 | 에이전트 활용 | 설정/운영 | 설정 시간 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | 내장 + 플랫폼 자료 | 내장 | 내장 | 플랫폼 memory + 대화 히스토리 + Memory Sources | 미확인: per-memory retrieval과 acted-on evidence는 platform-controlled입니다. | 내장 설정과 Memory Sources | 부분 지원 | 플랫폼 제어 | ChatGPT 플랫폼 전용, 외부 MCP/API/SDK 없음 | 낮음 | 공식: 즉시 |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | 내장 | 내장 프로젝트 지식 | 프로젝트용 내장 RAG | 프로젝트 지식 검색 | 부분 지원: project knowledge, file, tool log가 activation 일부를 보여주지만 custom receipt가 필요할 수 있습니다. | 내장 프로젝트 UI | 팀 요금제에서 내장 | 요금제/workspace 제어 | Claude + Claude Code + 커넥터 | 낮음-중간 | 공식: 몇 분 |
| [NotebookLM](../solutions/notebooklm.md) | 내장 | 내장 출처 요약과 라벨 | 부분 지원 | 출처 기반 notebook 채팅/검색 | 내장: bounded notebook에서는 source citation과 source selection으로 activated evidence가 보입니다. | 내장 notebook UI | 부분 지원 | 플랫폼 제어 | NotebookLM/Gemini 플랫폼 전용 | 낮음 | 공식: 몇 분 |

## 읽는 법

- `내장`은 제품이 해당 workflow를 직접 지원한다는 뜻이지만, 가져온 데이터에도 검토, 스키마 정리, 출처 라벨, 삭제 정책이 필요할 수 있습니다.
- `내장, 단 운영 필요`는 capability가 있지만 사용자가 설정, 동기화, 저장소, 유지보수 작업을 의미 있게 책임져야 한다는 뜻입니다.
- `연동`은 문서화된 커넥터, 플러그인, SDK, bridge가 있다는 뜻입니다.
- `커스텀 수집기`는 workflow는 가능하지만 사용자가 정보원별 코드, OAuth, rate limit, retry, normalization을 직접 책임져야 한다는 뜻입니다.
- `부분 지원`은 유용한 지원은 있지만 workflow가 불완전하거나 host에 의존하거나 특정 플랫폼에 묶여 있다는 뜻입니다.
- `주 용도 아님`은 억지로 쓸 수는 있지만 그 용도로 설계된 제품은 아닐 때 사용합니다.
- `미확인`은 아직 이 레포에서 검증하지 않은 주장이라는 뜻입니다.
- 설정 시간은 `공식`, `직접 설정`, `관리자/maintainer 추정`으로 구분합니다. 공식 quickstart는 있지만 신뢰할 수 있는 시간 추정이 없으면 실제 소요 시간이 달라진다고 표시합니다.
