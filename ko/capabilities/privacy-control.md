# 프라이버시와 통제권

## 이 기능 축의 의미

프라이버시, 이동성, 통제권은 memory가 어디에 저장되는지, 사용자가 확인하고 정정할 수 있는지, 삭제와 내보내기가 어떻게 동작하는지, 시스템을 self-host/export/audit할 수 있는지를 다룹니다.

## 평가 질문

- 사용자가 memory를 보고, 편집하고, 삭제하고, 내보낼 수 있는가?
- memory는 local, hosted, self-hosted 중 어디에 있는가?
- 출처와 근거가 보이는가?
- 사용자가 에이전트가 무엇을 쓸 수 있는지 통제할 수 있는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 부분 지원 | 호스팅형 통제, 대시보드 둘러보기, 프로젝트 지정, 삭제 흐름. | Memories 탭에서는 수동 생성/편집이 아직 불가능합니다. 내보내기, 보존, 삭제 요구사항을 확인하세요. |
| OpenHuman | 부분 지원 | 기본 경험에는 관리형 서비스가 포함되며 로컬 Memory Tree, Markdown vault, runtime state가 있습니다. | local-first가 기본적으로 완전 오프라인을 뜻하지는 않습니다. |
| GBrain | 내장 | 로컬/self-hosted 파일과 데이터베이스. | 사용자가 운영과 백업을 책임집니다. |
| Hermes Agent + LLM Wiki | wiki 파일 기준 내장 | wiki content는 사용자가 확인, 수정, 백업, 이동, 삭제할 수 있는 로컬 Markdown입니다. | 프라이버시는 Hermes runtime, model provider, browser/web extraction, 사용하는 sync service에 달려 있습니다. |
| Supermemory | 부분 지원 | 호스팅 앱, API, 커넥터 관리. | 커넥터 삭제 의미를 검토해야 합니다. |
| Hyperspell | 부분 지원 | user token, source connection control, metadata filter, folder skip/manual/sync policy, manual review flow, 홈페이지의 삭제 claim. | 기본적으로 hosted입니다. export, retention, deletion, plan-specific governance는 확인해야 합니다. |
| Honcho | self-hosting 기준 내장 | managed service 또는 self-hosted FastAPI server. workspace와 peer는 범위 지정 primitive를 제공합니다. | self-hosting은 더 많은 통제를 주지만 service, storage, provider key, update 운영을 추가합니다. |
| Mem0/OpenMemory | 내장 | hosted 또는 self-hosted. | self-hosting이 가장 강한 통제권을 제공합니다. |
| Zep/Graphiti | 부분 지원 | 호스팅형 Zep 또는 Graphiti library. | 플랫폼 보존 정책과 그래프 데이터 처리를 확인하세요. |
| Cognee | 로컬 모드에서 내장 | SDK/local mode, 선택적 Docker MCP 설정, 또는 API/Cloud mode. | 공유 API 모드는 통제 경계를 바꿉니다. |
| Khoj | self-hosting 시 내장 | cloud 또는 self-hosted. | cloud 편의성은 통제 경계를 바꿉니다. |
| Obsidian/Logseq + AI bridge | 내장 | 로컬 vault/graph와 백업. | 플러그인 권한이 위험을 키울 수 있습니다. |
| ChatGPT Memory | 부분 지원 | ChatGPT memory 설정, 삭제 제어, Temporary Chat, 연결된 앱/정보원 관리. | 플랫폼에 묶여 있고 기본적으로 portable하지 않습니다. 개인화 맥락을 완전히 제거하려면 관련 chat, file, connected-app data 삭제가 필요할 수 있습니다. |
| Claude Projects/Claude Code | 부분 지원 | 요금제, 프로젝트, 공유, workspace 통제. | 프로젝트 지식은 Claude 범위 안에 남습니다. |
| NotebookLM | 부분 지원 | 호스팅 notebook 통제와 출처 관리. | 일반 사용자에게 로컬 배포는 없습니다. |

## 출처

- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Hyperspell website](https://www.hyperspell.com/)
- [Honcho repository](https://github.com/plastic-labs/honcho)
- [Mem0 open-source overview](https://docs.mem0.ai/open-source/overview)
- [Khoj docs](https://docs.khoj.dev/)
