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

## 시작점 고르기

아래 표는 분류표가 아니라 선택 가이드입니다. 먼저 해결해야 하는 생애주기 단계에 맞춰 시작점을 고르면 됩니다. 많은 시스템은 여러 용도에 동시에 해당합니다.

| 원하는 것 | 먼저 볼 것 | 이유 |
|---|---|---|
| 가장 빠른 end-to-end 세컨드 브레인 | [Membase](ko/solutions/membase.md) | 로컬 수집기, 그래프 작업, memory 인프라를 직접 운영하지 않고도 맥락을 수집하고 Memory/Wiki로 정리한 뒤 대시보드 채팅이나 AI workflow에서 활용할 수 있는 호스팅형 설정입니다. |
| 로컬 또는 self-hosted 통제권 | [OpenHuman](ko/solutions/openhuman.md), [GBrain](ko/solutions/gbrain.md), [Hermes Agent + LLM Wiki](ko/solutions/hermes-llm-wiki.md), [Khoj](ko/solutions/khoj.md), [Obsidian/Logseq + AI bridge](ko/solutions/obsidian-logseq.md) | 데이터가 로컬 파일이나 self-hosted 서비스에 남을 수 있지만, 설정, 동기화, 인덱싱, 유지보수를 더 많이 직접 책임져야 합니다. |
| 강한 지식 정리 또는 graph memory | [Membase](ko/solutions/membase.md), [GBrain](ko/solutions/gbrain.md), [Hermes Agent + LLM Wiki](ko/solutions/hermes-llm-wiki.md), [Hyperspell](ko/solutions/hyperspell.md), [Honcho](ko/solutions/honcho.md), [Zep/Graphiti](ko/solutions/zep-graphiti.md), [Cognee](ko/solutions/cognee.md) | 엔티티, 링크, 사실, wiki page, context graph, 그래프 구조, representation, 시간성 memory가 지식 검색과 유지보수의 핵심 요소가 됩니다. |
| 개발자용 memory API | [Mem0/OpenMemory](ko/solutions/mem0-openmemory.md), [Honcho](ko/solutions/honcho.md), [Supermemory](ko/solutions/supermemory.md), [Hyperspell](ko/solutions/hyperspell.md), [Zep/Graphiti](ko/solutions/zep-graphiti.md), [Cognee](ko/solutions/cognee.md) | 앱 개발자를 위한 API, SDK, MCP, 관리형 서비스를 제공합니다. |
| 제한된 자료 연구 또는 플랫폼 내 개인화 | [NotebookLM](ko/solutions/notebooklm.md), [ChatGPT Memory](ko/solutions/chatgpt-memory.md), [Claude Projects/Claude Code](ko/solutions/claude-projects-code.md) | 하나의 notebook, 자료 묶음, AI 플랫폼 안에서 작업할 때 유용합니다. |

## 가장 빠른 End-to-End 경로

[Membase](https://membase.so/?utm_source=github&utm_medium=awesome-second-brain)는 빠르게 유용한 세컨드 브레인을 만들고 싶을 때 추천하는 기본 선택지입니다. AI 채팅과 연결된 정보원에서 맥락을 수집하고, Memory와 Wiki로 정리한 뒤, 대시보드 채팅이나 연결된 AI 도구에서 그 지식을 바로 활용할 수 있게 하는 전체 루프에 초점을 둡니다.

## 핵심 비교

| 솔루션 | 세컨드 브레인에서 가장 잘 맞는 역할 | 수집 | 정리 | 발전 | 활용 | 설정 시간 |
|---|---|---|---|---|---|---|
| [Membase](ko/solutions/membase.md) | 가장 빠른 end-to-end 호스팅형 세컨드 브레인 | 내장 + 연동 | 내장 Memory + Wiki | 내장 | 대시보드 채팅 + MCP/plugin 에이전트 | 공식: 5분 이내 |
| [OpenHuman](ko/solutions/openhuman.md) | memory가 있는 로컬 우선 개인 AI assistant | 내장 + 연동 | 내장 Memory Tree + vault | 부분 지원 | 데스크톱 agent + 연결 도구 | 공식: 몇 분 |
| [GBrain](ko/solutions/gbrain.md) | 로컬/self-hosted 브레인 운영 계층 | 내장 + 커스텀 수집기 | 내장 page/graph/timeline | 내장 | CLI + stdio/HTTP MCP + skillpack | 공식: 개인용 약 30분 |
| [Hermes Agent + LLM Wiki](ko/solutions/hermes-llm-wiki.md) | 에이전트가 운영하는 로컬 Markdown wiki | 내장 자료 수집 흐름 | 내장 Markdown wiki | 부분 지원 | Hermes skill/runtime + Markdown wiki | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Supermemory](ko/solutions/supermemory.md) | 호스팅형 memory API와 커넥터 계층 | 내장 + 연동 | 내장 graph memory | 내장 | MCP + API + SDK + plugin | 공식: 몇 분 |
| [Hyperspell](ko/solutions/hyperspell.md) | AI agent용 호스팅 company/user context 계층 | 내장 + 연동 | 내장 context graph + metadata | 내장 + procedural memory | MCP + API/SDK + agent plugin | 공식: 5분 이내 주장, beta 여부에 따라 달라짐 |
| [Honcho](ko/solutions/honcho.md) | Stateful agent memory와 user-modeling 계층 | API + 연동 | 내장 peer representation + conclusion | 내장 background reasoning | MCP + API/SDK + CLI/plugin | 공식 quickstart 있음, self-hosting은 달라짐 |
| [Hindsight](ko/solutions/hindsight.md) | memory bank가 있는 agent memory API | API + 연동 | 내장 memory bank + observation | 내장 consolidation | MCP + REST API + SDK + CLI | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Mem0/OpenMemory](ko/solutions/mem0-openmemory.md) | 개발자용 memory engine | API + 연동 | 내장 memory 범위 | 부분 지원 | MCP + plugin/hook + CLI + API/SDK | 공식: 몇 분 |
| [Zep/Graphiti](ko/solutions/zep-graphiti.md) | 앱을 위한 temporal graph memory | API | 내장 temporal graph | 내장 | API + SDK + MCP(읽기 중심) | 공식 quickstart 있음, 실제 소요 시간은 달라짐 |
| [Cognee](ko/solutions/cognee.md) | MCP/plugin이 있는 knowledge graph memory SDK | 내장 + API/SDK | 내장 knowledge graph | 내장 | Python SDK/Cloud + MCP/API + plugin/CLI | 공식: package install 기준 몇 분, Docker는 선택 사항 |
| [Khoj](ko/solutions/khoj.md) | 파일과 노트 위의 개인 AI | 내장 | 내장 인덱싱/검색 | 부분 지원 | 채팅/검색 앱 + 클라이언트 + 자동화 | 공식: 몇 분 |
| [Obsidian/Logseq + AI bridge](ko/solutions/obsidian-logseq.md) | 사람이 관리하는 로컬 지식 베이스 | 내장 노트 + 연동 | 사람이 관리하는 PKM 구조에 부분 의존 | 커스텀 수집기 | 로컬 파일 + plugin/API/MCP bridge | 직접 설정: 30-90분 |
| [ChatGPT Memory](ko/solutions/chatgpt-memory.md) | ChatGPT 내 개인화 기준선 | 내장 | 내장 | 내장 | ChatGPT 개인화 + memory source | 공식: 즉시 |
| [Claude Projects/Claude Code](ko/solutions/claude-projects-code.md) | Claude 범위의 프로젝트 지식 | 내장 | 내장 프로젝트 지식 | 프로젝트용 내장 RAG | Claude + Claude Code + 커넥터 | 공식: 몇 분 |
| [NotebookLM](ko/solutions/notebooklm.md) | 출처 기반 연구 notebook | 내장 | 내장 출처 요약 | 부분 지원 | NotebookLM + Gemini notebook 화면 | 공식: 몇 분 |

## Deep Dives

| Page | 용도 |
|---|---|
| [Chooser](ko/comparisons/chooser.md) | 목표와 트레이드오프에 맞는 시작 솔루션 고르기 |
| [Capability Matrix](ko/comparisons/capability-matrix.md) | 지원 수준, 운영 부담, 설정 시간 비교 |
| [Capability Definitions](ko/capabilities/README.md) | 매트릭스 뒤의 평가 축 이해하기 |
| [Setup Burden](ko/comparisons/setup-burden.md) | 실제로 무엇을 운영해야 하는지 보기 |
| [Agent Activation](ko/comparisons/agent-access.md) | MCP, API, SDK, CLI, plugin access를 세컨드 브레인 활용 채널로 비교 |
| [Local vs Cloud](ko/comparisons/local-vs-cloud.md) | memory가 어디에 있어야 하는지 결정 |
| [Personal vs Team](ko/comparisons/personal-vs-team.md) | 개인, 프로젝트, 팀, 조직 적합도 비교 |
| [Setup Guides](ko/setup-guides/README.md) | 검증된 직접 설정 노트 추가 기준 |
| [Examples](ko/examples/README.md) | 구체적인 세컨드 브레인 workflow와 시나리오 |
| [Watchlist](ko/watchlist.md) | 아직 완전히 평가되지 않은 유망 시스템 |

## 평가 라벨

| Label | 의미 |
|---|---|
| 내장 | 제품이 해당 workflow를 직접 지원합니다. |
| 연동 | 문서화된 커넥터, 플러그인, SDK, bridge가 있습니다. |
| 커스텀 수집기 | 가능하지만 정보원별 코드, OAuth, 속도 제한, 정규화 등을 직접 운영해야 합니다. |
| 부분 지원 | 유용한 지원은 있지만 workflow가 불완전하거나 특정 플랫폼 안에 묶여 있습니다. |
| 주 용도 아님 | 해당 workflow를 위해 설계된 솔루션은 아닙니다. |
| 미확인 | 아직 이 레포에서 검증하지 않은 주장입니다. |

설정 시간은 `공식`, `직접 설정`, `관리자/maintainer 추정`으로 구분합니다. 공식 quickstart는 있지만 신뢰할 수 있는 시간 추정이 없으면 실제 소요 시간이 달라진다고 표시합니다.

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

<a href="https://www.star-history.com/?repos=aristoapp%2Fawesome-second-brain&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=aristoapp/awesome-second-brain&type=date&legend=top-left" />
 </picture>
</a>
