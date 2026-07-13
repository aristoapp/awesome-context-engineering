# Personal vs Team

| 솔루션 | 개인 적합도 | 프로젝트 적합도 | 팀 적합도 | 메모 |
|---|---|---|---|---|
| [Membase](../solutions/membase.md) | 강함 | 강함 | 가능 / 출시 예정 | 현재는 Memory project와 Wiki collection으로 프로젝트 수준 범위 지정을 지원하고, 완전한 team/workspace 분리는 출시 예정입니다. |
| [OpenHuman](../solutions/openhuman.md) | 강함 | 가능 | 주 용도 아님 | 많은 연동이 있는 로컬 우선 개인 데스크톱 AI. |
| [GBrain](../solutions/gbrain.md) | 강함 | 강함 | 강함 / 운영 필요 | company-brain path는 source, source-scoped OAuth client, federated read, HTTP MCP, 보통 Postgres/Supabase를 사용합니다. 디렉터리만으로 나누는 scoping은 관례 기반입니다. |
| [obsidian-wiki](../solutions/obsidian-wiki.md) | 강함 | 강함 | 부분 지원 / 운영 필요 | named vault profile과 project page로 context를 나누지만 shared-vault sync, concurrent editing, permission, approval은 외부에서 해결해야 합니다. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | 강함 | 강함 | 부분 지원 / 운영 필요 | 여러 wiki 디렉터리, schema, vault, repo로 프로젝트를 나눌 수 있지만 팀 permission은 skill 바깥에서 해결해야 합니다. |
| [Supermemory](../solutions/supermemory.md) | 강함 | 강함 | 가능 | 프로젝트 범위 지정과 커넥터가 도움을 주지만 팀 거버넌스는 확인해야 합니다. |
| [Hyperspell](../solutions/hyperspell.md) | 강함 | 강함 | app builder에게 강함 | multi-tenant user model, user token, metadata, collection, source selection, folder policy가 도움을 주지만 governance UX는 app team이 책임져야 합니다. |
| [Honcho](../solutions/honcho.md) | 강함 | 강함 | app builder에게 강함 | workspace가 app/environment를 격리하고 peer/session이 user, agent, group 등 entity를 모델링할 수 있지만, 최종 사용자 governance UX는 app이 책임집니다. |
| [Mnemosyne](../solutions/mnemosyne.md) | 강함 | 강함 | 부분 지원 / 운영 필요 | Memory bank와 global/session scope로 context를 나눌 수 있지만, team permission과 review flow는 memory layer 바깥에서 해결해야 합니다. |
| [taOSmd](../solutions/taosmd.md) | 강함 | 강함 | 부분 지원 / 운영 필요 | Agent별 shelf와 cross-agent read가 context를 나눌 수 있지만, team permission과 review flow는 memory layer 바깥에서 해결해야 합니다. |
| [Vestige](../solutions/vestige.md) | 강함 | 강함 | 주 용도 아님 | per-project code memory와 local scoping으로 context를 나누지만 memory는 단일 machine의 local-only이며 team permission이나 shared-workspace product surface가 없습니다. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | 강함 | 강함 | 강함 | user, session, organizational memory 덕분에 제품에 넣기 좋습니다. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | 가능 | 강함 | 강함 | user, session, group, business data를 위한 앱 인프라로 가장 좋습니다. |
| [Cognee](../solutions/cognee.md) | 강함 | 강함 | API 모드에서 강함 | standalone mode는 client를 격리하고 API mode는 공유를 중앙화합니다. |
| [Khoj](../solutions/khoj.md) | 강함 | 가능 | 부분 지원 | 범용 팀 memory 계층보다 개인 AI에 더 적합합니다. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | 강함 | 강함 | 부분 지원 | source of truth로 훌륭하지만 팀 재사용은 sync, permission, bridge 규율에 의존합니다. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | 강함 | 부분 지원 | 부분 지원 | memory는 user/platform 범위에 묶이며 enterprise control은 workspace별로 다르고 memory source는 요금제/지역/설정에 의존합니다. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | 강함 | 강함 | Team/Enterprise에서 강함 | work plan에서 project knowledge base와 팀 공유를 지원합니다. |
| [NotebookLM](../solutions/notebooklm.md) | 강함 | 강함 | 부분 지원 | 공유 출처 분석에는 강하지만 기본적으로 살아 있는 팀 memory system은 아닙니다. |

## Guidance

개인 세컨드 브레인은 편의성과 소유권에 최적화할 수 있습니다. 팀 세컨드 브레인에는 명시적인 출처 경계, 접근 제어, 감사 가능성, 공유 memory를 누가 쓰고/정정하고/삭제할지에 대한 계획이 필요합니다.
