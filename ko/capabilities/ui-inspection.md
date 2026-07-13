# 검토와 정정

## 이 기능 축의 의미

검토와 정정은 사용자가 시스템이 무엇을 아는지 보고, 유용한 기준으로 필터링하고, 잘못된 memory를 바로잡으며, 정보원 가져오기나 에이전트 쓰기가 예상한 위치에 도착했는지 검증할 수 있는지를 다룹니다.

## 평가 질문

- 사용자가 memory를 둘러보고, 검색하고, 필터링하고, 편집하고, 삭제하고, 정정할 수 있는가?
- 출처, 날짜, 프로젝트, collection, workspace 필터가 보이는가?
- 수집, 동기화, 커넥터, 인덱싱 상태를 확인할 수 있는가?
- 주 인터페이스가 사람, 개발자, 에이전트 중 누구를 위해 만들어졌는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 내장 | 출처, 대시보드 채팅, memories, Memory graph/table view, Wiki graph/table view, 필터, 에이전트 설정용 대시보드. | Memories 탭에서는 둘러보기, 프로젝트 이동, 삭제는 가능하지만 수동 생성/편집은 아직 지원하지 않습니다. 내보내기, 보존 정책, 요금제별 거버넌스는 확인해야 합니다. |
| OpenHuman | 내장 | 데스크톱 UI, Memory Tree, Markdown vault, 온보딩, 음성, 앱 화면. | 초기 베타 동작은 직접 테스트해야 합니다. |
| GBrain | 부분 지원 | client registration, request log, job, live activity, scoped operation용 CLI와 HTTP admin surface. | 운영 상태 점검에는 유용하지만 polished Notion/Roam 스타일 지식 UI는 아닙니다. |
| Hermes Agent + LLM Wiki | 파일 기준 내장 | 사용자는 Markdown page, source folder, `index.md`, `log.md`, `SCHEMA.md`, frontmatter, confidence flag, contradiction marker를 확인하고 수정할 수 있습니다. | polished hosted dashboard는 없습니다. 검토는 파일, editor, Obsidian, git 같은 도구에서 이뤄집니다. |
| Supermemory | 내장 | 호스팅 앱, 콘솔, 커넥터 상태, 프로젝트, 필터. | 팀/관리자 점검은 요금제와 설정에 의존합니다. |
| Hyperspell | 부분 지원 | dashboard, list/get/update memory API, metadata filtering, indexing status, query error, webhook, evaluation API, folder manual-review state. | end-user second-brain UI는 대부분 app이 책임집니다. 대상 계정에서 dashboard visibility를 확인해야 합니다. |
| Honcho | 부분 지원 | API/MCP를 통한 developer-facing workspace, peer, session, conclusion, queue, metadata 도구. | polished end-user review와 correction UI는 통합 구현이 책임집니다. |
| Mnemosyne | 부분 지원 | CLI, export/import, update/delete/invalidate tool, diagnostics, scratchpad tool, local SQLite file이 operator inspection path를 제공합니다. | Hosted human-facing review dashboard는 주요 surface로 문서화되어 있지 않습니다. |
| taOSmd | 부분 지원 | `taosmd serve`가 제공하는 local web dashboard에서 search, pending-review list, health를 볼 수 있고 CLI와 append-only archive가 operator inspection path를 제공합니다. | Dashboard는 hosted multi-user review product가 아니라 local inspection surface입니다. |
| Vestige | 부분 지원 | embedded local 3D dashboard(`localhost:3927`)가 live event와 memory graph browsing을 제공하며 CLI와 `memory`/`contradictions`/`memory_status` tool로 inspection, correction, health 확인을 할 수 있습니다. | Dashboard는 hosted multi-user review product가 아니라 local single-user inspection surface입니다. |
| Mem0/OpenMemory | 내장 | 플랫폼 대시보드와 self-hosted 대시보드/서버 경로. | 애플리케이션 소유자가 사용자용 검토 흐름을 여전히 정의해야 합니다. |
| Zep/Graphiti | 부분 지원 | 개발자/플랫폼 UI와 그래프 API. | 최종 사용자를 위한 세컨드 브레인 UI가 주 표면은 아닙니다. |
| Cognee | 부분 지원 | 개발자/관리자 화면과 MCP 도구 레퍼런스. | 최종 사용자 점검은 대상 workflow에서 확인해야 합니다. |
| Khoj | 내장 | 웹, 데스크톱, 브라우저, 에디터/클라이언트 인터페이스. | 점검 방식은 정보원과 배포 선택에 의존합니다. |
| Obsidian/Logseq + AI bridge | 내장 | 그래프, backlink, 태그, 속성, 검색, 페이지, 블록. | 에이전트 쓰기에는 검토 규율이 필요합니다. |
| ChatGPT Memory | 내장 | Settings, Manage memories, memory 검색/정렬, memory history 복원, Memory Sources. | ChatGPT 플랫폼 memory와 지원되는 플랫폼 자료만 다룹니다. |
| Claude Projects/Claude Code | 내장 | Claude 프로젝트 UI, 지식 베이스, 지침, 공유 설정, RAG 표시. | 프로젝트 가시성은 workspace 요금제와 권한에 의존합니다. |
| NotebookLM | 내장 | notebook UI, 출처 패널, 출처 선택, 라벨/카테고리, 생성된 결과물. | 가져온 자료 점검에는 강하지만 완전한 세컨드 브레인 운영 UI는 아닙니다. |

## 출처

- [Membase Memory](https://docs.membase.so/features/memory)
- [Membase Chat in Dashboard](https://docs.membase.so/features/chat)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell list memories](https://docs.hyperspell.com/api-reference/memories/list-memories)
- [Hyperspell folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [ChatGPT Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq)
- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)
