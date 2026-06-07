# 배포와 소유권

## 이 기능 축의 의미

배포와 소유권은 memory가 어디에 있고, 누가 저장소와 인덱싱을 운영하며, 사용자가 인프라, 인증, 모델, 데이터 보관 위치를 얼마나 통제할 수 있는지를 정의합니다.

## 평가 질문

- 시스템은 hosted, local, self-hosted, platform-bound, hybrid 중 무엇인가?
- 저장소, 인덱스, 임베딩, 커넥터, MCP/API 서버는 누가 운영하는가?
- 팀이 데이터 보관 위치, 백업, self-hosted 인프라를 선택할 수 있는가?
- 배포 모델이 공유, 프라이버시, 설정 부담을 바꾸는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | Hosted | 계정 + 호스팅 memory 계층 + remote MCP. | 설정이 빠르지만 인프라 통제권은 적습니다. |
| OpenHuman | 로컬 + 관리형 서비스 혼합 | 관리형 로그인, 모델 라우팅, 검색 프록시, OAuth 흐름이 있는 데스크톱 로컬 상태. | local-first가 기본적으로 완전 오프라인을 뜻하지는 않습니다. |
| GBrain | Local/self-hosted | 개인용 brain은 local PGLite. 공유형, 대규모, remote deployment는 Postgres/Supabase와 stdio/HTTP MCP. | PGLite는 단일 사용자 로컬 운영에 가장 적합합니다. shared/team deployment에는 database, OAuth, sync, job, storage 운영이 추가됩니다. |
| Hermes Agent + LLM Wiki | Local/server-owned | Hermes는 사용자가 통제하는 인프라에서 실행되고, wiki는 `WIKI_PATH` 또는 `~/wiki`의 Markdown 디렉터리입니다. | model provider, web extraction, browser use, sync 선택에 따라 cloud dependency가 생길 수 있습니다. |
| Supermemory | Hosted + API | 호스팅 MCP, API, SDK, 커넥터. | self-hosting/control 세부 사항은 대상 요금제에서 확인해야 합니다. |
| Hyperspell | Hosted + API | hosted dashboard, memory/context platform, SDK, API, MCP server, 공개 plugin/SDK repo. | 핵심 memory platform은 managed입니다. private beta 사용 가능 여부와 data residency/retention 세부 사항을 확인해야 합니다. |
| Mem0/OpenMemory | Hosted/self-hosted | hosted Mem0 Platform 또는 open-source server/library 경로. | self-hosting에도 memory 인프라 결정이 필요합니다. |
| Zep/Graphiti | Hosted + OSS library | Zep managed platform 또는 Graphiti library 연동. | 플랫폼과 library는 관련되어 있지만 같은 표면은 아닙니다. |
| Cognee | SDK/local/API mode | local database를 쓰는 Python package/SDK, 선택적 local/Docker MCP 설정, 또는 공유 API/Cloud mode. | 모드 선택이 memory 격리와 공유에 영향을 줍니다. |
| Khoj | Cloud/self-hosted | Khoj Cloud 또는 self-hosted 개인 AI. | self-hosting에는 모델/정보원 설정이 필요합니다. |
| Obsidian/Logseq + AI bridge | Local-first | local vault/graph와 선택적 sync, 플러그인, bridge. | agent memory에는 추가 bridge 또는 가져오기 경로가 필요합니다. |
| ChatGPT Memory | Hosted platform | ChatGPT 설정과 플랫폼 memory. | 일반 사용자에게 로컬 또는 portable deployment는 없습니다. |
| Claude Projects/Claude Code | Hosted platform + local agent | Claude project와 로컬 Claude Code runtime. | 프로젝트 지식은 플랫폼에 호스팅됩니다. |
| NotebookLM | Hosted platform | Google-hosted notebook과 자료. | 일반 사용자에게 로컬 배포는 없습니다. |

## 출처

- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Hermes Agent website](https://hermes-agent.nousresearch.com/)
- [Hyperspell docs](https://docs.hyperspell.com/)
- [Hyperspell GitHub org](https://github.com/hyperspell)
- [Mem0 open-source overview](https://docs.mem0.ai/open-source/overview)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
