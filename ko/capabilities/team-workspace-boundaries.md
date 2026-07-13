# 개인/팀 범위

## 이 기능 축의 의미

개인/팀 범위는 개인, 프로젝트, workspace, 팀, 조직 맥락 전반에서 누가 memory를 읽고, 쓰고, 업데이트하고, 삭제하고, 공유할 수 있는지를 정의합니다.

## 평가 질문

- 프로젝트, collection, source, user, session, group, workspace를 지원하는가?
- 읽기와 쓰기가 범위 지정되는가?
- 팀이 개인 memory를 노출하지 않고 지식을 공유할 수 있는가?
- 관리자가 접근을 감사하거나 회수할 수 있는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 부분 지원 | 범위 지정 검색/필터링을 위한 Memory project tag와 Wiki collection. | 완전한 team/workspace 분리는 출시 예정입니다. 대상 요금제의 거버넌스 세부 사항을 확인하세요. |
| OpenHuman | 주 용도 아님 | 개인 로컬 앱과 연결된 정보원. | team/workspace 거버넌스가 핵심 용도는 아닙니다. |
| GBrain | 내장, 단 운영 필요 | brain, source, source-scoped OAuth client, federated read, mount, Postgres/Supabase, HTTP MCP. | 디렉터리만으로 나누는 범위 지정은 관례 기반입니다. 강제되는 팀 격리에는 명시적인 source/OAuth 설계가 필요합니다. |
| Hermes Agent + LLM Wiki | 부분 지원 | 별도 wiki 디렉터리, schema, vault, repo로 프로젝트 경계를 만들 수 있습니다. | permission, shared review, team governance는 외부 파일시스템/sync/운영 프로세스 문제입니다. |
| Supermemory | 연동 | 프로젝트 범위 지정과 커넥터 메타데이터. | 팀 거버넌스는 확인해야 합니다. |
| Hyperspell | app builder 기준 내장 | multi-tenant app user ID, user token, source selection, metadata, collection, resource filter, folder policy. | team/workspace governance UX는 app이 책임집니다. 계정/plan 동작은 확인해야 합니다. |
| Honcho | app builder 기준 내장 | workspace가 app/environment를 격리하고 peer/session이 user, agent, group 등 entity를 모델링합니다. | 최종 사용자 governance UX와 permission flow는 app이 책임집니다. |
| Mnemosyne | 부분 지원 | Memory bank와 global/session scope가 domain 또는 agent context를 분리할 수 있습니다. | Team permission, admin control, review workflow는 memory backend 바깥에서 해결해야 합니다. |
| taOSmd | 부분 지원 | Agent별 shelf와 cross-agent read가 agent context와 project를 나눕니다. | Team permission, admin control, review workflow는 memory layer 일부가 아닙니다. |
| Vestige | 부분 지원 | Per-project code memory와 local scoping으로 context를 분리합니다. | Memory는 단일 machine의 local-only이며 team permission, admin control, shared-workspace review는 memory layer 일부가 아닙니다. |
| Mem0/OpenMemory | 내장 | user, session, 조직 memory. | 신중한 범위 설계가 필요합니다. |
| Zep/Graphiti | 내장 | project, user, session, group. | 앱 인프라로 사용할 때 가장 좋습니다. |
| Cognee | API 모드에서 내장 | 공유 backend/API 모드. | standalone 모드는 클라이언트를 격리합니다. |
| Khoj | 부분 지원 | 배포 방식과 정보원 선택. | 주로 개인용입니다. |
| Obsidian/Logseq + AI bridge | 부분 지원 | 공유 vault/sync와 권한. | 팀 memory 규율은 사용자가 책임집니다. |
| ChatGPT Memory | 부분 지원 | workspace/admin 동작은 ChatGPT 요금제와 설정에 의존합니다. | portable team memory로 설계되지는 않았습니다. |
| Claude Projects/Claude Code | 팀 요금제에서 내장 | Team/Enterprise 프로젝트 공유와 권한. | 범위는 Claude 프로젝트/workspace 중심입니다. |
| NotebookLM | 부분 지원 | 공유/협업은 Google 계정과 제품 tier에 의존합니다. | notebook 경계는 완전한 세컨드 브레인 거버넌스가 아닙니다. |

## 출처

- [Membase attached vs universal memory](https://docs.membase.so/core-concepts/attached-vs-universal)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell core concepts](https://docs.hyperspell.com/core/concepts)
- [Hyperspell folder sync](https://docs.hyperspell.com/usage/folder-sync)
- [Honcho overview](https://honcho.dev/docs/v3/documentation/introduction/overview)
- [Mnemosyne repository](https://github.com/AxDSan/Mnemosyne)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Mem0 memory types](https://docs.mem0.ai/core-concepts/memory-types)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
