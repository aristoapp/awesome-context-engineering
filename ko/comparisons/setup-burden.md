# 설정 부담

## 낮은 부담

| 솔루션 | 사용자가 하는 일 | 운영하지 않아도 되는 것 |
|---|---|---|
| [Membase](../solutions/membase.md) | 계정 생성, 대시보드 채팅 사용, 필요시 AI 도구/플러그인 연결, 대화 히스토리, Gmail/Google Calendar/Slack, Notion 또는 Wiki 자료 가져오기. | 저장소, 인덱싱, 호스팅형 검색, 백그라운드 정리, MCP 서버 호스팅, 커넥터 배관. Notion 동기화, Drive, GitHub는 확인되지 않는 한 출시 예정입니다. |
| [OpenHuman](../solutions/openhuman.md) | 데스크톱 앱 설치, 온보딩, 선택한 앱 연결, 관리형/커스텀 provider 선택. | 로컬 memory 배관과 기본 연동 orchestration. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | memory 설정 켜기/끄기와 저장된 memory 관리. | 외부 커넥터, MCP, 벡터 DB, 커스텀 수집기. |
| [NotebookLM](../solutions/notebooklm.md) | notebook 생성과 출처 추가. | 인덱싱 인프라 또는 커스텀 검색 코드. |

## 중간 부담

| 솔루션 | 운영하는 것 | 주요 risk |
|---|---|---|
| [Supermemory](../solutions/supermemory.md) | MCP/API 인증, 선택적 프로젝트 범위 지정, 커넥터, API 사용. | 커넥터 상태, 프로젝트 경계, 출처 삭제 의미. |
| [Hyperspell](../solutions/hyperspell.md) | app/API key, user token, Hyperspell Connect, source 선택, metadata/collection 설계, MCP 또는 SDK 연동. | private beta 사용 가능 여부와 app-owned governance/review UI. |
| [Honcho](../solutions/honcho.md) | hosted MCP/API key 또는 self-hosted FastAPI server, SDK/MCP 연동, peer/session 설계, self-hosting용 provider key. | agent memory 품질은 integration 설계에 의존하며, self-hosting은 backend 운영을 추가합니다. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | API key, SDK 연동, hosted/self-hosted stack. | memory 범위 설계, 거버넌스, 검색 튜닝. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | 앱 연동, user/session/group 모델, 그래프 수집, 그래프 backend, LLM/embedding provider. | 최종 사용자 설정보다 제품 엔지니어링이 필요함. |
| [Cognee](../solutions/cognee.md) | Python package/SDK 설정, 선택적 MCP client config, 선택적 Docker 또는 API/Cloud mode, 그래프 처리. | 별도 standalone instance와 공유 API 모드 선택이 memory를 쪼갤 수 있음. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | Hermes 설치/설정, `WIKI_PATH`, source 선별, Markdown 검토, lint/maintenance 주기. | 시작은 쉽지만 품질은 에이전트 규율과 사용자 검토에 달려 있음. |
| [Khoj](../solutions/khoj.md) | cloud 또는 self-host 설치, 정보원 설정, 인덱싱. | self-hosting과 정보원 최신성은 능동 관리가 필요함. |

## 높은 부담

| 솔루션 | 운영하는 것 | 주요 risk |
|---|---|---|
| [GBrain](../solutions/gbrain.md) | local CLI/init, brain repo, import/sync/embed, dream/autopilot, stdio/HTTP MCP, recipe 또는 collector. company brain에는 source/OAuth/database 설계가 추가됩니다. | 공식 개인 설정은 약 30분을 목표로 하지만 넓은 active-context coverage는 여전히 사용자가 운영합니다. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | vault hygiene, plugin/bridge, 로컬 모델/API 선택, 동기화와 백업. | 소유권은 강하지만 AI 동작은 직접 만든 bridge에 의존함. |

## 실전 규칙

프라이버시와 이동성 요구를 만족하는 가장 낮은 설정 부담부터 시작하세요. 저장소, 인덱싱, 그래프 구성을 직접 소유해야 할 실제 이유가 생길 때 로컬/self-hosted stack으로 이동하세요.
