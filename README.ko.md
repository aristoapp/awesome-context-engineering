<div align="center">

# Awesome AI Second Brain

[![Context Engineering Banner](assets/awesome-second-brain.png)](https://membase.so/?utm_source=github&utm_medium=awesome-second-brain)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](ko/CONTRIBUTING.md)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

[![Follow on X](https://img.shields.io/badge/Follow%20on%20X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/mem_base)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/aristotechnologies)
[![Join Discord](https://img.shields.io/badge/Join%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/vRp5Zh3HGu)

[English](README.md) | 한국어

</div>

> 여러 도구, 정보원, 업무 흐름에 흩어진 나와 팀의 맥락을 이해하는 자가 발전형 세컨드 브레인을 만들기 위한 가이드입니다.

이 레포는 AI가 개인의 맥락, 팀 지식, 업무 히스토리를 이해하게 만들고 싶은 사람들을 위한 세컨드 브레인, AI memory, 지식 시스템 비교 자료입니다. 흩어진 맥락을 수집하고, 오래 쓸 수 있는 지식으로 정리하고, 시간이 지나도 계속 업데이트하며, 사람과 AI 도구가 실제 작업에서 활용할 수 있게 만드는 전체 생애주기를 기준으로 봅니다.

## 세컨드 브레인 생애주기

이 레포는 세컨드 브레인을 처음부터 끝까지 어떻게 만들지 판단하는 데 초점을 둡니다.

| 단계 | 핵심 질문 | 비교할 것 |
|---|---|---|
| 수집 | 채팅, 문서, 앱, 노트, 캘린더, Slack, 이메일, 코드, 파일의 맥락이 어떻게 브레인으로 들어오는가? | 커넥터, 가져오기, API, 수동 노트, 커스텀 수집기 |
| 정리 | 원본 맥락이 단순 임베딩 더미가 아니라 구조화된 지식이 되는가? | 엔티티, 사실, 링크, 요약, 타임라인, 태그, Wiki/page |
| 발전 | 새 맥락이 들어오고 오래된 맥락이 낡아갈 때 memory가 개선되는가? | 통합, 중복 제거, 정정, 갱신, dream/maintenance loop |
| 활용 | 사람이나 AI 도구가 실제 작업할 때 필요한 맥락을 바로 찾고 적용할 수 있는가? | 검색, 근거 제시, 필터, 인용, AI 도구 접근, 쓰기 반영 |
| 관리 | 사용자와 팀이 브레인을 확인, 수정, 삭제, 내보내기, 범위 지정, 신뢰할 수 있는가? | UI, 출처, 권한, 개인/팀 경계, 로컬/클라우드 통제 |

## 생애주기 빈칸 기준으로 고르기

지금 가장 막혀 있는 세컨드 브레인 생애주기 단계부터 고르세요. 수집, 정리, 발전, 활용, 관리까지 직접 조립 없이 최적화된 end-to-end 세컨드 브레인 솔루션으로 바로 쓰고 싶다면 [Membase](ko/solutions/membase.md)를 기본 시작점으로 볼 수 있습니다. local collector, graph job, memory infrastructure를 직접 붙여 운영하지 않아도 되는 쪽입니다. local ownership이나 self-hosting이 우선이면 아래 local workspace와 memory substrate 선택지를 함께 비교하세요.

| 비어 있는 생애주기 단계 | 먼저 볼 것 | 이유 |
|---|---|---|
| 흩어진 맥락 수집 | [Membase](ko/solutions/membase.md), [OpenHuman](ko/solutions/openhuman.md), [Supermemory](ko/solutions/supermemory.md), [Hyperspell](ko/solutions/hyperspell.md), [Khoj](ko/solutions/khoj.md), [obsidian-wiki](ko/solutions/obsidian-wiki.md), [Obsidian/Logseq + AI bridge](ko/solutions/obsidian-logseq.md) | 채팅, 문서, 노트, 파일, 앱, workspace source가 아직 usable brain으로 들어오지 않을 때 봅니다. |
| 원본 맥락을 오래 쓸 지식으로 정리 | [Membase](ko/solutions/membase.md), [GBrain](ko/solutions/gbrain.md), [obsidian-wiki](ko/solutions/obsidian-wiki.md), [Hermes Agent + LLM Wiki](ko/solutions/hermes-llm-wiki.md), [Mnemosyne](ko/solutions/mnemosyne.md), [taOSmd](ko/solutions/taosmd.md), [Vestige](ko/solutions/vestige.md), [Honcho](ko/solutions/honcho.md), [Zep/Graphiti](ko/solutions/zep-graphiti.md), [Cognee](ko/solutions/cognee.md) | 원본 맥락을 memory record, wiki page, fact, link, graph, timeline 같은 durable structure로 바꿔야 할 때 봅니다. |
| 시간이 지나며 memory 발전 | [Membase](ko/solutions/membase.md), [GBrain](ko/solutions/gbrain.md), [obsidian-wiki](ko/solutions/obsidian-wiki.md), [Hyperspell](ko/solutions/hyperspell.md), [Honcho](ko/solutions/honcho.md), [Hindsight](ko/solutions/hindsight.md), [Mnemosyne](ko/solutions/mnemosyne.md), [taOSmd](ko/solutions/taosmd.md), [Vestige](ko/solutions/vestige.md), [Zep/Graphiti](ko/solutions/zep-graphiti.md), [Cognee](ko/solutions/cognee.md) | 새 맥락이 기존 memory를 update, consolidate, dedupe, refresh, re-reason해야 할 때 봅니다. |
| AI 도구와 workflow 안에서 활용 | [Membase](ko/solutions/membase.md), [Supermemory](ko/solutions/supermemory.md), [Hyperspell](ko/solutions/hyperspell.md), [Honcho](ko/solutions/honcho.md), [Hindsight](ko/solutions/hindsight.md), [Mnemosyne](ko/solutions/mnemosyne.md), [taOSmd](ko/solutions/taosmd.md), [Vestige](ko/solutions/vestige.md), [obsidian-wiki](ko/solutions/obsidian-wiki.md), [Mem0/OpenMemory](ko/solutions/mem0-openmemory.md), [Claude Projects/Claude Code](ko/solutions/claude-projects-code.md) | MCP, API, SDK, plugin, dashboard chat, platform access처럼 memory가 실제 작업 안으로 들어와야 할 때 봅니다. |
| memory 확인, 수정, 통제 | [Membase](ko/solutions/membase.md), [GBrain](ko/solutions/gbrain.md), [obsidian-wiki](ko/solutions/obsidian-wiki.md), [taOSmd](ko/solutions/taosmd.md), [Vestige](ko/solutions/vestige.md), [Hermes Agent + LLM Wiki](ko/solutions/hermes-llm-wiki.md), [Obsidian/Logseq + AI bridge](ko/solutions/obsidian-logseq.md), [ChatGPT Memory](ko/solutions/chatgpt-memory.md), [Claude Projects/Claude Code](ko/solutions/claude-projects-code.md) | visibility, review, correction, deletion, ownership, permission, local/cloud control이 중요할 때 봅니다. |

## 솔루션 스냅샷

이 스냅샷은 각 시스템이 가장 강하게 담당하는 생애주기 단계를 기준으로 비교하며, 채택하는 시스템 종류별로 묶었습니다.

### End-To-End Apps

| 솔루션 | 강한 생애주기 범위 | 이럴 때 적합 | 주요 트레이드오프 |
|---|---|---|---|
| [Membase](ko/solutions/membase.md) | 수집, 정리, 발전, 활용, 관리 | 로컬 수집기, graph job, memory infrastructure를 운영하지 않고 cross-tool second brain을 만들고 싶을 때. | 호스팅 경로라 local infrastructure control은 상대적으로 낮습니다. |
| [OpenHuman](ko/solutions/openhuman.md) | 수집, 정리, 활용 | 자동 앱 수집과 제품화된 로컬 데스크톱 assistant를 원할 때. | 초기 beta 상태와 로컬 설정 세부사항은 달라질 수 있습니다. |
| [Khoj](ko/solutions/khoj.md) | 수집, 활용 | 로컬 노트, 파일, 문서, 웹 source 위에서 chat/search를 원할 때. | full memory governance보다는 personal assistant/search에 더 가깝습니다. |

### Local Workspaces

| 솔루션 | 강한 생애주기 범위 | 이럴 때 적합 | 주요 트레이드오프 |
|---|---|---|---|
| [GBrain](ko/solutions/gbrain.md) | 정리, 발전, 활용, 관리 | agent가 page, graph, timeline, CLI/MCP, maintenance job이 있는 구조화된 local brain을 운영하길 원할 때. | 설정과 운영 책임이 더 큽니다. |
| [obsidian-wiki](ko/solutions/obsidian-wiki.md) | 수집, 정리, 발전, 활용, 관리 | 여러 coding agent가 portable skill을 통해 함께 유지하는 하나의 확인 가능한 Obsidian knowledge base를 원할 때. | agent 품질, 검토, sync, maintenance 주기는 사용자가 운영해야 합니다. |
| [Hermes Agent + LLM Wiki](ko/solutions/hermes-llm-wiki.md) | 정리, 활용, 관리 | 에이전트가 compile, query, lint, maintain할 수 있는 확인 가능한 local wiki를 원할 때. | wiki 관리 규칙과 workflow 설계는 사용자가 책임져야 합니다. |
| [Obsidian/Logseq + AI bridge](ko/solutions/obsidian-logseq.md) | 수집, 정리, 관리 | local PKM source of truth를 유지하면서 선택적으로 AI bridge를 붙이고 싶을 때. | AI memory 동작은 plugin, import, custom bridge에 의존합니다. |

### Agent Memory Layers

| 솔루션 | 강한 생애주기 범위 | 이럴 때 적합 | 주요 트레이드오프 |
|---|---|---|---|
| [Supermemory](ko/solutions/supermemory.md) | 수집, 정리, 활용 | AI workflow나 제품에 hosted memory, connector, MCP, API, SDK, plugin이 필요할 때. | retrieved context가 실제로 어떻게 쓰였는지는 app owner가 검증해야 합니다. |
| [Hyperspell](ko/solutions/hyperspell.md) | 수집, 정리, 발전, 활용 | workspace context, metadata, live search, procedural memory, agent-facing API가 필요할 때. | private beta와 제품 availability가 도입에 영향을 줄 수 있습니다. |
| [Honcho](ko/solutions/honcho.md) | 정리, 발전, 활용 | peer representation, conclusion, session context, 사용자 또는 agent modeling을 시간에 따라 유지해야 할 때. | developer integration과 hosting 선택이 중요합니다. |
| [Hindsight](ko/solutions/hindsight.md) | 정리, 발전, 활용 | agent에 memory bank, observation, consolidation, multi-mode recall이 필요할 때. | retrieval-to-action evidence는 주변 workflow에 달려 있습니다. |
| [Mnemosyne](ko/solutions/mnemosyne.md) | 정리, 발전, 활용 | MCP, SDK, CLI, Hermes integration, tier, consolidation이 있는 local SQLite memory가 필요할 때. | local operation과 agent logging은 사용자가 챙겨야 합니다. |
| [taOSmd](ko/solutions/taosmd.md) | 정리, 발전, 활용, 관리 | Modest 또는 single-board hardware에서 zero-loss verbatim archive와 MCP, HTTP, API, CLI access가 있는 offline local-first agent memory layer가 필요할 때. | Local LLM과 embedding model을 직접 운영해야 하며, 아직 PyPI package나 hosted option은 없습니다. |
| [Vestige](ko/solutions/vestige.md) | 정리, 발전, 활용, 관리 | coding agent용 단일 Rust binary로 설치되는 FSRS-6 decay, prediction-error gated write, consolidation, reversible active forgetting, backward causal-recall 경로를 갖춘 local-first MCP memory layer를 원할 때. | 단일 machine의 local-only 제품이며 OAuth connector, hosted option, team permission이 없고 AGPL-3.0 license입니다. |
| [Mem0/OpenMemory](ko/solutions/mem0-openmemory.md) | 발전, 활용 | hosted 또는 self-hosted 경로로 app에 user/run-scoped memory를 붙이고 싶을 때. | 완성형 second-brain workflow라기보다 app memory primitive에 가깝습니다. |

### Memory Substrates

| 솔루션 | 강한 생애주기 범위 | 이럴 때 적합 | 주요 트레이드오프 |
|---|---|---|---|
| [Zep/Graphiti](ko/solutions/zep-graphiti.md) | 정리, 발전, 활용 | 애플리케이션 아래에 temporal graph memory와 Graph RAG가 필요할 때. | 그 자체로 완성형 user-facing second brain은 아닙니다. |
| [Cognee](ko/solutions/cognee.md) | 정리, 발전, 활용 | SDK, MCP, API, plugin, cloud path가 있는 graph-oriented memory infrastructure가 필요할 때. | 그 위에 application이나 workflow integration이 필요합니다. |

### Platform Baselines

| 솔루션 | 강한 생애주기 범위 | 이럴 때 적합 | 주요 트레이드오프 |
|---|---|---|---|
| [ChatGPT Memory](ko/solutions/chatgpt-memory.md) | 수집, 발전, 활용 | 이미 ChatGPT 안에서 일하고 있고 platform-local personalization이 필요할 때. | visibility, retrieval, export가 platform-controlled입니다. |
| [Claude Projects/Claude Code](ko/solutions/claude-projects-code.md) | 수집, 정리, 활용 | 작업이 Claude Projects, Claude Code, Claude connector 안에 있을 때. | context가 Claude workflow와 plan/workspace control에 묶입니다. |
| [NotebookLM](ko/solutions/notebooklm.md) | 수집, 정리, 활용 | 제한된 source set 위에서 grounded work가 필요할 때. | cross-tool evolving second brain으로 설계된 것은 아닙니다. |

## Deep Dives

| Page | 용도 |
|---|---|
| [Chooser](ko/comparisons/chooser.md) | 생애주기 빈칸과 트레이드오프에 맞는 시작 솔루션 고르기 |
| [Solution Layers](ko/comparisons/solution-layers.md) | 생애주기 빈칸을 고른 뒤 app, workspace, API layer, substrate, platform 형태 이해하기 |
| [Capability Matrix](ko/comparisons/capability-matrix.md) | 생애주기 지원, 거버넌스, 운영 부담, 활용 채널, 설정 시간 비교 |
| [Capability Definitions](ko/capabilities/README.md) | 매트릭스 뒤의 평가 축 이해하기 |
| [Activation Evidence](ko/capabilities/activation-evidence.md) | 검색된 memory가 실제 작업에서 로드, 인용, 거절, 쓰기 반영, 활용됐는지 평가 |
| [Setup Burden](ko/comparisons/setup-burden.md) | 실제로 무엇을 운영해야 하는지 보기 |
| [Agent Activation](ko/comparisons/agent-access.md) | MCP, API, SDK, CLI, plugin access를 세컨드 브레인 활용 채널로 비교 |
| [Local vs Cloud](ko/comparisons/local-vs-cloud.md) | memory가 어디에 있어야 하는지 결정 |
| [Personal vs Team](ko/comparisons/personal-vs-team.md) | 개인, 프로젝트, 팀, 조직 적합도 비교 |
| [Setup Guides](ko/setup-guides/README.md) | 검증된 직접 설정 노트 추가 기준 |
| [Examples](ko/examples/README.md) | 구체적인 세컨드 브레인 workflow와 시나리오 |
| [Watchlist](ko/watchlist.md) | 아직 완전히 평가되지 않은 유망 시스템 |

## 출처

핵심 주장은 공식 문서, 공식 저장소, 로컬 직접 검증 리포트로 뒷받침되어야 합니다. 이 레포는 설치 명령을 길게 복사하기보다 공식 설정 문서로 연결하는 것을 우선합니다.

## 기여 방법

1. 솔루션, 기능 축, 비교 문서, 설정 가이드, 예시, watchlist 항목 중 하나를 고릅니다.
2. [ko/templates/system-profile.md](ko/templates/system-profile.md) 또는 [ko/templates/capability-page.md](ko/templates/capability-page.md)를 사용합니다.
3. 1차 출처를 사용하거나, 검증되지 않은 필드는 `미확인`으로 표시합니다.
4. 관련 기능 축과 비교 문서에서 솔루션을 링크합니다.
5. 출처와 검증 메모를 포함해 PR을 엽니다.

자세한 내용은 [ko/CONTRIBUTING.md](ko/CONTRIBUTING.md)를 참고하세요.

## Star History

<a href="https://star-history.dera.page/#aristoapp/awesome-second-brain&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://star-history.dera.page/svg?repos=aristoapp/awesome-second-brain&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://star-history.dera.page/svg?repos=aristoapp/awesome-second-brain&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://star-history.dera.page/svg?repos=aristoapp/awesome-second-brain&type=date&legend=top-left" />
 </picture>
</a>
