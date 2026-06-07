# 기능 매트릭스

라벨: `내장`, `내장, 단 운영 필요`, `연동`, `커스텀 수집기`, `부분 지원`, `주 용도 아님`, `미확인`.

| 솔루션 | 맥락 수집 | 지식 정리 | Memory 발전 | 검색/활용 | 검토/정정 | 개인/팀 범위 | 프라이버시/통제권 | 에이전트 활용 | 설정/운영 | 설정 시간 |
|---|---|---|---|---|---|---|---|---|---|---|
| [Membase](../solutions/membase.md) | 내장 + 연동 | 내장 Memory + Wiki | 내장 | Memory용 graph + vector hybrid RAG, Wiki용 vector + keyword hybrid search, 대시보드 채팅 | 내장 대시보드 제어 | 부분 지원: project/collection 범위 지정, team/workspace 분리는 출시 예정 | 호스팅형 제어 | MCP + 플러그인 + 대시보드 채팅 | 낮음 | 공식: 5분 이내 |
| [OpenHuman](../solutions/openhuman.md) | 내장 + 연동 | 내장 Memory Tree + Markdown vault | 부분 지원 | 로컬 Memory Tree + vault + memory graph | 내장 데스크톱 화면 | 주 용도 아님 | 로컬 memory + 관리형 서비스 | 데스크톱 agent + skill/tool + 선택적 agentmemory backend | 낮음-중간 | 공식: 몇 분 |
| [GBrain](../solutions/gbrain.md) | 내장 + 커스텀 수집기 | 내장 page/graph/timeline/schema | 내장 | 저비용 hybrid search + 확장 query + `think` 종합 | 부분 운영/관리 UI | 내장, 단 운영 필요 | 로컬/self-hosted 통제 | CLI + stdio/HTTP MCP + agent skillpack | 중간-높음 | 공식: 개인용 약 30분 |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | 내장 | 내장 Markdown wiki/schema/index/log | 부분 지원 | wiki orientation + Markdown file search + page synthesis | 내장 Markdown 검토 + lint workflow | 부분 지원 | 로컬/사용자 서버 파일 | Hermes 번들 skill/runtime | 중간 | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Supermemory](../solutions/supermemory.md) | 내장 + 연동 | 내장 graph memory | 내장 | Memory API + hybrid search + graph memory | 내장 hosted app/console | 연동 | 호스팅형 제어 | MCP + API + SDK + plugin | 낮음-중간 | 공식: 몇 분 |
| [Hyperspell](../solutions/hyperspell.md) | 내장 + 연동 | 내장 context graph + metadata | 내장 + procedural memory | indexed/live search + grounded answer + API action | API review flow + app-owned UI | 내장 user model | 호스팅형 제어 | MCP + API/SDK + agent plugin | 낮음-중간 | 공식: 5분 이내 주장, beta 여부에 따라 달라짐 |
| [Honcho](../solutions/honcho.md) | API + 연동 | 내장 peer representation + conclusion | 내장 background reasoning | Search + context + representation | 부분 개발자/API 도구 | 내장 peer/workspace model | Hosted 또는 self-hosted | MCP + API/SDK + CLI/client plugin | 중간 | 공식 quickstart 있음, self-hosting은 달라짐 |
| [Hindsight](../solutions/hindsight.md) | API + 연동 | 내장 memory bank + observation | 내장 consolidation | semantic/keyword/graph/temporal recall + reflect | 부분 개발자/API 도구 | 부분 memory-bank scoping | Cloud, Docker, package, embedded server, local MCP | MCP + REST API + SDK + CLI | 중간 | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | API + 연동 | 내장 memory 범위 | 부분 지원 | Layered memory search + auto context injection | 내장 dashboard/server 경로 | 내장 | Hosted 또는 self-hosted | MCP + plugin/hook + CLI + API/SDK | 중간 | 공식: 몇 분 |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | API | 내장 temporal graph | 내장 | Temporal knowledge graph + Graph RAG | 부분 개발자 UI/API | 내장 | Hosted 또는 OSS library 경로 | API + SDK + MCP(읽기 중심) | 중간 | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Cognee](../solutions/cognee.md) | 내장 + API/SDK | 내장 knowledge graph | 내장 | Knowledge graph memory | 부분 개발자/관리자 화면 | API 모드에서 내장 | SDK/local mode, 선택적 Docker, self-hosted API 또는 Cloud SDK | Python SDK/Cloud + MCP/API + plugin/CLI | 중간 | 공식: package install 기준 몇 분, Docker는 선택 사항 |
| [Khoj](../solutions/khoj.md) | 내장 | 내장 인덱싱/검색 | 부분 지원 | 파일, 노트, 문서, 웹 위의 채팅과 자연어 검색 | 내장 앱/클라이언트 UI | 부분 지원 | Cloud 또는 self-hosted | Web/app client + 내장 agent/automation | 중간 | 공식: 몇 분 |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | 내장 노트 + 연동 | 사람이 관리하는 PKM 구조에 부분 의존 | 커스텀 수집기 | 로컬 search/graph + plugin RAG | 내장 사람 검토 UI | 부분 지원 | 로컬 vault/graph 통제 | 로컬 파일 + plugin/API/MCP bridge | 중간-높음 | 직접 설정: 30-90분 |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | 내장 + 플랫폼 자료 | 내장 | 내장 | 플랫폼 memory + 대화 히스토리 + Memory Sources | 내장 설정과 Memory Sources | 부분 지원 | 플랫폼 제어 | ChatGPT 플랫폼 전용, 외부 MCP/API/SDK 없음 | 낮음 | 공식: 즉시 |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | 내장 | 내장 프로젝트 지식 | 프로젝트용 내장 RAG | 프로젝트 지식 검색 | 내장 프로젝트 UI | 팀 요금제에서 내장 | 요금제/workspace 제어 | Claude + Claude Code + 커넥터 | 낮음-중간 | 공식: 몇 분 |
| [NotebookLM](../solutions/notebooklm.md) | 내장 | 내장 출처 요약과 라벨 | 부분 지원 | 출처 기반 notebook 채팅/검색 | 내장 notebook UI | 부분 지원 | 플랫폼 제어 | NotebookLM/Gemini 플랫폼 전용 | 낮음 | 공식: 몇 분 |

## 읽는 법

- `내장`이 항상 자동으로 좋은 품질을 보장한다는 뜻은 아닙니다. 가져온 데이터에도 검토, 스키마 정리, 출처 라벨, 삭제 정책이 필요할 수 있습니다.
- `연동`은 문서화된 커넥터, 플러그인, SDK, bridge가 있다는 뜻입니다.
- `커스텀 수집기`는 workflow는 가능하지만 사용자가 정보원별 코드, OAuth, rate limit, retry, normalization을 직접 책임져야 한다는 뜻입니다.
- `주 용도 아님`은 억지로 쓸 수는 있지만 그 용도로 설계된 제품은 아닐 때 사용합니다.
