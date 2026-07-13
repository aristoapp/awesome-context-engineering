# 맥락 수집

## 이 기능 축의 의미

맥락 수집은 AI 대화, 노트, 문서, 이메일, 캘린더, Slack, Drive, Notion, 브라우저 데이터, 코드, 커스텀 이벤트 같은 개인/팀/정보원 맥락이 세컨드 브레인으로 들어오는 방식을 뜻합니다.

## 평가 질문

- 수집 방식이 내장 기능, 커넥터, API, 커스텀 구현 중 무엇인가?
- 출처, 시각, 권한 정보를 보존하는가?
- 원본 가져오기와 정리된 memory를 구분하는가?
- 필요한 히스토리를 잃지 않고 정보원 연결을 끊을 수 있는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 내장 + 연동 | 에이전트 쓰기, 대시보드 채팅, ChatGPT/Claude/Gemini 대화 가져오기, Gmail/Google Calendar/Slack, Obsidian/Markdown Wiki 가져오기, Notion 가져오기. | Notion 동기화, Drive, GitHub는 특정 계정에서 확인되지 않는 한 출시 예정으로 다루세요. |
| OpenHuman | 내장 + 연동 | 118개 이상의 OAuth 연동, 자동 가져오기, 로컬 Memory Tree, Markdown vault. | 베타 동작과 커넥터 신뢰성은 직접 검증이 필요합니다. |
| GBrain | 내장 + 커스텀 수집기 | Markdown 가져오기, `capture`, 파일/stdin 캡처, HTTP `/ingest`, inbox 폴더, `sync --watch` 폴링, recipe, skillpack ingestion source. | 외부 API에는 recipe 또는 커스텀 수집기 작업이 필요합니다. `sync --watch`는 스트리밍이 아니라 폴링입니다. |
| Hermes Agent + LLM Wiki | 내장 자료 수집 흐름 | 번들 skill이 URL, PDF, 붙여넣은 텍스트, 파일, article, paper, transcript, asset을 `raw/`에 넣는 capture path를 정의합니다. | 넓은 OAuth 커넥터 계층은 아닙니다. 자료 수집은 에이전트/사용자 작업 흐름 중심입니다. |
| Supermemory | 내장 + 연동 | MCP/API와 Drive, Gmail, Notion, OneDrive, GitHub, Web Crawler. | 커넥터 권한, 동기화 상태, container/project 태그가 중요합니다. |
| Hyperspell | 내장 + 연동 | Hyperspell Connect, workspace integration, manual add, bulk ingestion, file upload, web crawler, folder sync policy, trace ingestion. | private beta/계정별 사용 가능 여부가 다릅니다. app owner가 source, metadata, user scoping을 직접 선택해야 합니다. |
| Honcho | API + 연동 | API/SDK/MCP write로 message, session, uploaded document를 추가합니다. | 넓은 외부 source capture는 통합하는 app 또는 agent에 달려 있습니다. |
| Mnemosyne | API + 연동 | MCP/CLI/SDK write, Python `remember`, memory bank, Hermes lifecycle hook이 agent context를 수집할 수 있습니다. | 넓은 OAuth connector 계층은 아니며 capture는 agent, hook, developer 주도입니다. |
| taOSmd | API + 연동 | Python API, HTTP/REST, MCP write가 각 turn을 append-only archive에 verbatim으로 기록하고 vector/knowledge graph indexing을 그 위에 얹습니다. | Capture는 agent/developer 주도이며 넓은 OAuth connector 계층은 아닙니다. |
| Vestige | MCP + 연동 | `smart_ingest`와 agent-memory protocol을 통한 MCP/CLI write를 지원하며, `source_sync`가 외부 source(문서에는 GitHub Issues)를 local index에 넣습니다. | Capture는 agent/developer 주도이며 넓은 OAuth connector 계층은 아닙니다. |
| Mem0/OpenMemory | API + 연동 | 앱 또는 AI workflow에서 SDK/API/MCP로 쓰기. | 수집 설계는 애플리케이션이 책임집니다. |
| Zep/Graphiti | API | 대화 히스토리, 비즈니스 데이터, 그래프 엔드포인트. | 앱 연동이 필요합니다. |
| Cognee | 내장 + API | MCP memory/data 도구와 그래프 처리. | standalone 모드와 shared 모드에 따라 데이터가 저장되는 위치가 달라집니다. |
| Khoj | 내장 | 파일, 노트, PDF, Markdown, org-mode, Notion page. | 여러 도구 전체의 맥락 수집보다는 개인 자료 Q&A에 더 적합합니다. |
| Obsidian/Logseq + AI bridge | 내장 노트 + 연동 | 로컬 노트와 플러그인/가져오기/파일시스템 bridge. | 에이전트가 바로 쓸 수 있는 수집 품질은 bridge에 의존합니다. |
| ChatGPT Memory | 내장 + 플랫폼 자료 | 저장된 memory, 대화 히스토리 참조, 요금제/지역/설정에 따라 custom instructions, 파일, 연결된 Gmail 같은 Memory Sources. | 일반적인 외부 정보원 수집 백엔드는 아닙니다. |
| Claude Projects/Claude Code | 내장 | 프로젝트 업로드, 프로젝트 지침, 대화 맥락, 활성화된 커넥터. | 외부 memory를 추가하지 않으면 Claude 범위 안에 묶입니다. |
| NotebookLM | 내장 | 문서, PDF, 웹 URL, YouTube, 오디오, Gemini Chats, Fast Research, Deep Research 등 지원 자료 유형의 업로드/가져오기/탐색. | 가져온 자료는 유형에 따라 제한적이거나 정적일 수 있고, 지원되는 Drive 자료는 자동 동기화될 수 있습니다. |

## 출처

- [Membase overview](https://docs.membase.so/)
- [Membase app integrations](https://docs.membase.so/connectors/apps)
- [Membase Obsidian connector](https://docs.membase.so/connectors/obsidian)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Supermemory connectors](https://supermemory.ai/docs/connectors/overview)
- [Hyperspell integrations](https://docs.hyperspell.com/integrations/overview)
- [Hyperspell Connect](https://docs.hyperspell.com/usage/connect)
- [Honcho overview](https://honcho.dev/docs/v3/documentation/introduction/overview)
- [Mnemosyne docs](https://docs.mnemosyne.site/)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Khoj docs](https://docs.khoj.dev/)
