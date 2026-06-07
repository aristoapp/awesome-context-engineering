# 설정과 운영

## 이 기능 축의 의미

설정과 운영은 최초 설치, 인증, 정보원 동기화, 인덱싱, 재시도, 백그라운드 작업, 검증, 업그레이드, 지속 유지보수를 다룹니다.

## 평가 질문

- 처음 쓸 만한 memory까지 얼마나 걸리는가?
- 어떤 런타임과 계정이 필요한가?
- 저장소, 임베딩, MCP 서버, 수집기는 누가 운영하는가?
- 사용자는 설정이 실제로 동작하는지 어떻게 알 수 있는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 내장 | 계정 + 대시보드 채팅, 선택적으로 AI 도구/플러그인 연결. | 가장 빠른 경로지만 호스팅형 트레이드오프가 있습니다. |
| OpenHuman | 내장 + 연동 | 네이티브 데스크톱 설치, 온보딩, 앱 연결, provider 선택. | 초기 베타입니다. 커넥터 설정이 범위를 늘릴 수 있습니다. |
| GBrain | 내장 + 커스텀 수집기 | CLI/init, brain repo, import/sync/embed 작업, dream/autopilot, stdio/HTTP MCP. company brain에는 source/OAuth/database 설계가 추가됩니다. | 공식 agent install은 개인용 기준 약 30분을 목표로 하지만 production source coverage는 여전히 운영 부담이 큽니다. |
| Hermes Agent + LLM Wiki | 내장 skill | Hermes 설치/설정, 필요시 `WIKI_PATH` 설정, source 선별, Markdown output 검토, lint 또는 maintenance pass 실행. | Hermes에는 빠른 설치 경로가 있지만 wiki 품질은 운영과 검토에 의존합니다. |
| Supermemory | 내장 + 연동 | MCP/API와 커넥터. | 커넥터 상태와 프로젝트 범위 지정이 중요합니다. |
| Hyperspell | 내장 + 연동 | dashboard/API key, SDK/API 또는 MCP 설정, app user ID 또는 user token, Hyperspell Connect, source 선택, metadata/scope 설계. | 공식 5분 이내 claim은 demo에는 가능해 보이지만 production setup은 beta access, app integration, governance 선택에 따라 달라집니다. |
| Honcho | 연동 | hosted MCP/API key 또는 self-hosted FastAPI server, SDK/MCP 연동, peer/session 설계, self-hosting용 provider key. | hosted agent 설정은 빠르지만 production integration과 self-hosting은 backend 운영을 추가합니다. |
| Mem0/OpenMemory | 연동 | hosted MCP/API 또는 self-hosted stack. | memory 설계는 애플리케이션 작업입니다. |
| Zep/Graphiti | API | 앱 연동, 그래프 수집, 그래프 backend, LLM/embedding provider 설정. | 빌더 중심입니다. 공식 quickstart는 있지만 backend 선택에 따라 실제 소요 시간이 달라집니다. |
| Cognee | 내장 | Python package/SDK 설정, 선택적 MCP config, 선택적 Docker 또는 API/Cloud mode. | Docker는 필수가 아니며, 모드를 신중히 선택해야 합니다. |
| Khoj | 내장 | cloud 또는 self-host와 정보원. | 정보원 최신성 검증이 필요합니다. |
| Obsidian/Logseq + AI bridge | 연동 | 노트 앱과 플러그인/가져오기/MCP bridge. | 소유권은 강하지만 설정 선택지가 더 많습니다. |
| ChatGPT Memory | 내장 | ChatGPT memory 설정 켜기/관리. | 즉시 쓸 수 있지만 플랫폼에 묶입니다. |
| Claude Projects/Claude Code | 내장 + 연동 | 프로젝트 생성, 지식 추가, 공유/커넥터 설정 또는 Claude Code 사용. | 커넥터와 팀 동작은 요금제에 의존합니다. |
| NotebookLM | 내장 | notebook 생성 후 지원되는 자료 추가. | 출처 갱신 동작은 자료 유형에 의존합니다. |

## 출처

- [Membase quickstart](https://docs.membase.so/getting-started/quickstart)
- [Hermes Agent website](https://hermes-agent.nousresearch.com/)
- [Hyperspell quickstart](https://docs.hyperspell.com/core/quickstart)
- [Hyperspell manual integration](https://docs.hyperspell.com/core/integration)
- [Supermemory MCP setup](https://supermemory.ai/docs/supermemory-mcp/setup)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
- [Cognee installation](https://docs.cognee.ai/getting-started/installation)
