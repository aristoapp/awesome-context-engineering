# Solutions

솔루션 프로필은 각 제품이나 프로젝트가 AI-native 세컨드 브레인에서 어떤 역할을 할 수 있는지 설명합니다. 이 문서들은 전체 지형을 이해하기 위한 프로필이며, 공식 설정 문서를 대체하지 않습니다.

링크 안정성을 위해 프로필 파일은 한 디렉터리에 유지하지만, 아래 목록은 주 계층별로 묶습니다. 일부 시스템은 여러 계층에 걸쳐 있지만, 여기서는 이 레포가 먼저 평가하는 역할을 기준으로 분류합니다.

## End-To-End Apps

수집, 정리, 검색, 사용자-facing workflow가 함께 패키징된 시스템입니다.

| 솔루션 | 세컨드 브레인에서 가장 잘 맞는 역할 | 상태 |
|---|---|---|
| [Membase](membase.md) | 가장 빠른 end-to-end 호스팅형 세컨드 브레인 | 핵심 |
| [OpenHuman](openhuman.md) | 자동 memory 수집이 있는 로컬 우선 개인 AI | 핵심, 초기 베타 |
| [Khoj](khoj.md) | 로컬 파일과 노트 위의 개인 AI | 핵심 |

## Local Workspaces

사용자와 에이전트가 확인하거나 유지보수할 수 있는 로컬 파일, wiki page, vault, self-hosted brain 운영을 중심에 둔 시스템입니다.

| 솔루션 | 세컨드 브레인에서 가장 잘 맞는 역할 | 상태 |
|---|---|---|
| [GBrain](gbrain.md) | 로컬 또는 self-hosted 브레인 운영 계층 | 핵심, 직접 검증 |
| [obsidian-wiki](obsidian-wiki.md) | Obsidian용 agent-agnostic local knowledge-compilation framework | 핵심, 출처 기반 |
| [Hermes Agent + LLM Wiki](hermes-llm-wiki.md) | 에이전트가 운영하는 로컬 Markdown wiki | 핵심 |
| [Obsidian/Logseq + AI bridge](obsidian-logseq.md) | 로컬 우선 PKM 원본 지식 저장소 | 핵심 |

## Agent Memory Layers

에이전트와 제품에 memory를 붙이기 위한 API, SDK, MCP server, 관리형 서비스를 제공하는 시스템입니다.

| 솔루션 | 세컨드 브레인에서 가장 잘 맞는 역할 | 상태 |
|---|---|---|
| [Supermemory](supermemory.md) | 호스팅형 memory API와 커넥터 계층 | 핵심 |
| [Hyperspell](hyperspell.md) | AI agent용 호스팅 company/user context 계층 | 핵심, private beta 주의 |
| [Honcho](honcho.md) | Stateful agent memory와 user-modeling 계층 | 핵심, 출처 기반 |
| [Hindsight](hindsight.md) | memory bank가 있는 agent memory API | 핵심, 출처 기반 |
| [Mnemosyne](mnemosyne.md) | MCP와 Hermes 연동이 있는 local-first agent memory layer | 핵심, 출처 기반 |
| [taOSmd](taosmd.md) | zero-loss archive가 있는 local-first offline agent memory layer | 핵심, 출처 기반 |
| [Vestige](vestige.md) | FSRS-6 decay, active forgetting, backward causal recall을 갖춘 local-first agent memory layer | 핵심, 출처 기반 |
| [Mem0/OpenMemory](mem0-openmemory.md) | hosted/self-hosted 경로가 있는 개발자용 memory 계층 | 핵심 |

## Memory Substrates

애플리케이션이 그 위에 구축하는 graph, retrieval, knowledge infrastructure에 가까운 시스템입니다.

| 솔루션 | 세컨드 브레인에서 가장 잘 맞는 역할 | 상태 |
|---|---|---|
| [Zep/Graphiti](zep-graphiti.md) | 애플리케이션을 위한 temporal knowledge graph memory | 핵심 |
| [Cognee](cognee.md) | MCP/plugin이 있는 knowledge graph memory SDK | 핵심 |

## Platform Baselines

하나의 AI platform 또는 제한된 research surface 안에서 유용한 기준선입니다.

| 솔루션 | 세컨드 브레인에서 가장 잘 맞는 역할 | 상태 |
|---|---|---|
| [ChatGPT Memory](chatgpt-memory.md) | ChatGPT 내 개인화 기준선 | 기준선 |
| [Claude Projects/Claude Code](claude-projects-code.md) | Claude 범위의 프로젝트 지식과 개발자 맥락 | 기준선 |
| [NotebookLM](notebooklm.md) | 출처 기반 연구 notebook 기준선 | 기준선 |

## 프로필 작성 규칙

모든 프로필은 배포/소유권, 맥락 수집, 지식 정리, memory 발전, 검색/활용, 검토/정정, 개인/팀 범위, 프라이버시/통제권, 에이전트 활용/쓰기 반영, 설정/운영, 잘 맞는 사용자, 잘 맞지 않는 사용자, 트레이드오프, 공식 설정/평가 링크를 다뤄야 합니다. 출처로 뒷받침되지 않는 주장은 `미확인`으로 표시하세요.
