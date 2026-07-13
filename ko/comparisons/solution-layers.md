# 솔루션 계층

세컨드 브레인 제품, agent memory API, retrieval substrate는 자주 함께 언급되지만 같은 stack 계층에 있지는 않습니다. 완성형 앱을 backend infrastructure처럼 평가하거나, memory substrate에 완전한 사용자 workflow를 기대하지 않도록 이 페이지를 먼저 확인하세요. 사용자가 먼저 채택하는 대상이 앱인지, workspace인지, API layer인지, substrate인지, platform feature인지에 따라 분류합니다.

## 계층 모델

| 계층 | 주 역할 | 주요 사용자 | 비교할 것 |
|---|---|---|---|
| End-to-end app | 수집, 정리, 검색, UI, workflow 활용을 함께 패키징합니다. | AI power user, 팀, 운영자 | 유용한 상태까지 걸리는 시간, source coverage, 지식 UI, 거버넌스, 연동 |
| Local workspace | 로컬 파일, vault, wiki page, self-hosted service에 사람이 소유하거나 에이전트가 운영하는 지식 베이스를 둡니다. | Local-first 사용자, 연구자, 기술 운영자 | 확인 가능성, 파일 소유권, sync model, 유지보수 부담, agent access |
| Agent memory layer | API, SDK, MCP, plugin, 관리형 서비스를 통해 에이전트나 애플리케이션에 durable memory를 붙입니다. | 개발자, agent builder, 내부 platform team | API 사용성, scope, write-back, retrieval 품질, traceability, hosting model |
| Memory substrate | 앱이 그 위에 구축하는 graph, retrieval, entity, temporal, knowledge infrastructure를 제공합니다. | infrastructure team, backend engineer, framework builder | data model, retrieval architecture, update semantics, scaling, 운영 복잡도 |
| Platform baseline | 하나의 AI platform 또는 제한된 research surface 안에서 memory나 source-grounded context를 제공합니다. | 특정 platform 안에서 이미 일하는 사용자 | platform 적합도, export 가능성, visibility, source control, lock-in |

## 주 계층별 평가 솔루션

| 계층 | 솔루션 |
|---|---|
| End-to-end app | [Membase](../solutions/membase.md), [OpenHuman](../solutions/openhuman.md), [Khoj](../solutions/khoj.md) |
| Local workspace | [GBrain](../solutions/gbrain.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md), [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) |
| Agent memory layer | [Mem0/OpenMemory](../solutions/mem0-openmemory.md), [Honcho](../solutions/honcho.md), [Hindsight](../solutions/hindsight.md), [Mnemosyne](../solutions/mnemosyne.md), [Supermemory](../solutions/supermemory.md), [Hyperspell](../solutions/hyperspell.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md) |
| Memory substrate | [Zep/Graphiti](../solutions/zep-graphiti.md), [Cognee](../solutions/cognee.md) |
| Platform baseline | [ChatGPT Memory](../solutions/chatgpt-memory.md), [Claude Projects/Claude Code](../solutions/claude-projects-code.md), [NotebookLM](../solutions/notebooklm.md) |

## 계층이 다른 솔루션을 같이 읽는 법

하나의 솔루션이 여러 decision path에 등장하더라도, 계층 라벨은 고정된 경계가 아니라 주 역할을 뜻합니다.

- End-to-end app은 사용자가 infrastructure를 조립하지 않고 흩어진 맥락에서 실제 작업까지 갈 수 있는지로 봅니다.
- Local workspace는 사용자가 지식 베이스를 장기적으로 확인, 수정, 동기화, 운영할 수 있는지로 봅니다.
- Agent memory layer는 개발자가 agent workflow 안에서 memory를 안전하게 scope 지정, 검색, 업데이트, 감사할 수 있는지로 봅니다.
- Memory substrate는 다른 애플리케이션이 그 위에 구축할 수 있는 data/retrieval primitive를 제공하는지로 봅니다.
- Platform baseline은 해당 platform 안에서 충분히 유용한지, workflow가 platform 밖으로 나가야 할 때 어떤 제약이 생기는지로 봅니다.

## 자주 쓰이는 조합

현실적인 배포에서는 여러 계층을 함께 쓰는 경우가 많습니다.

| 패턴 | 예시 |
|---|---|
| App + platform baseline | cross-tool memory는 완성형 second-brain app에 두고, ChatGPT Memory나 Claude Projects는 platform-local personalization으로 유지합니다. |
| Local workspace + agent memory layer | durable note는 wiki나 vault에 두고, session memory와 recall은 agent memory API를 사용합니다. |
| Agent memory layer + memory substrate | product memory는 API layer로 만들고, 그 아래 graph/retrieval infrastructure에 의존합니다. |
| Local workspace + memory substrate | 확인 가능한 source of truth는 local wiki나 vault에 두고, application use를 위해 graph/retrieval infrastructure로 index합니다. |

## 기여 규칙

새 시스템을 추가할 때는 사용자가 실제로 먼저 채택하는 가장 작은 주 계층을 고르세요. 프로젝트가 주로 graph, database, embedding index, retrieval backend라면 완성형 second-brain app처럼 소개하지 말고 memory substrate 또는 watchlist 후보로 넣는 편이 낫습니다. 여러 계층에 걸친 시스템이라면 primary adoption surface를 먼저 표시하고, 부수적인 역할은 profile 안에서 설명하세요.
