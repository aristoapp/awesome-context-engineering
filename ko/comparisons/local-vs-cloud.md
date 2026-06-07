# Local vs Cloud

| 솔루션 | Local / self-hosted | Hosted / cloud | 선택할 가장 좋은 이유 | 주요 트레이드오프 |
|---|---|---|---|---|
| [Membase](../solutions/membase.md) | 주 모델은 아님 | 예 | stack을 운영하지 않고 빠르게 end-to-end 세컨드 브레인을 만들기 | 로컬 인프라 통제권이 적음. |
| [OpenHuman](../solutions/openhuman.md) | 예, 로컬 memory/runtime state와 Markdown vault | 예, 로그인, 모델 라우팅, 검색 프록시, OAuth/연동용 관리형 서비스 | 제품화된 로컬 우선 개인 AI | local-first가 기본적으로 완전 오프라인을 뜻하지는 않음. |
| [GBrain](../solutions/gbrain.md) | 예, local PGLite와 self-hosted Postgres/Supabase 경로 | HTTP MCP는 원격 배포 가능 | 세컨드 브레인 운영에 대한 최대 통제권 | PGLite는 로컬 개인 사용에 적합합니다. shared/team deployment에는 Postgres/Supabase, OAuth, sync, embedding, collector, maintenance가 추가됩니다. |
| [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md) | 예, 로컬/서버 Hermes runtime과 Markdown wiki 디렉터리 | 선택한 hosting, sync, model provider에 따라 선택적으로 사용 | 확인 가능한 에이전트 유지보수형 wiki | 관리형 connector/governance 계층은 없고, wiki hygiene과 runtime configuration은 사용자가 책임집니다. |
| [Supermemory](../solutions/supermemory.md) | API/self-hosting 세부 사항은 제품 경로에 따라 다름 | 예 | 커넥터가 있는 hosted memory API | 호스팅 편의성과 플랫폼 경계. |
| [Hyperspell](../solutions/hyperspell.md) | 공개 SDK/MCP/plugin 레포는 있지만 핵심 memory platform은 hosted | 예 | agent용 hosted connector, context graph, retrieval layer | private beta 사용 가능 여부와 낮은 로컬 인프라 통제권. |
| [Honcho](../solutions/honcho.md) | 예, self-hosted FastAPI server | 예, managed service와 hosted MCP | hosted 또는 직접 소유 배포 경로가 있는 stateful agent memory | self-hosting에는 service, provider key, storage, update 운영이 추가됨. |
| [Mem0/OpenMemory](../solutions/mem0-openmemory.md) | OSS/self-hosted 설정으로 가능 | Mem0 Platform으로 가능 | hosted 또는 직접 소유 stack을 가진 개발자용 memory 계층 | memory 범위와 거버넌스 설계 필요. |
| [Zep/Graphiti](../solutions/zep-graphiti.md) | Graphiti는 open source, Zep은 managed | 예 | 앱을 위한 temporal graph memory | 제품 엔지니어링과 backend/provider 선택 필요. |
| [Cognee](../solutions/cognee.md) | 예, SDK/local 설정과 선택적 Docker MCP | 예, API/Cloud mode/shared backend | MCP/plugin이 있는 knowledge graph memory SDK | 모드 선택이 공유와 격리에 영향. |
| [Khoj](../solutions/khoj.md) | 예 | 예 | 프라이버시 선택지가 있는 파일 기반 개인 AI | self-hosting에도 정보원/모델 설정 필요. |
| [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md) | 예 | 선택적 sync/service | 사람이 소유하는 로컬 노트 | AI memory에는 plugin 또는 custom bridge 필요. |
| [ChatGPT Memory](../solutions/chatgpt-memory.md) | 아니오 | 예 | ChatGPT 내장 개인화 | 플랫폼에 묶이고 portable하지 않음. |
| [Claude Projects/Claude Code](../solutions/claude-projects-code.md) | Claude Code에는 로컬 terminal/IDE/desktop surface가 있고, 프로젝트 지식은 플랫폼에 호스팅됨 | 예 | Claude-native 프로젝트 맥락과 개발자 에이전트 workflow | 외부 MCP memory를 추가하지 않으면 플랫폼 범위 안에 묶임. |
| [NotebookLM](../solutions/notebooklm.md) | 아니오 | 예 | 출처 기반 research notebook | 정적으로 가져온 출처와 플랫폼에 묶인 workflow. |

## Guidance

local-first 시스템은 소유권, 감사 가능성, 커스텀 스키마 작업, 오래 유지할 개인 아카이브에 더 좋습니다. hosted 시스템은 설정 속도, OAuth 커넥터, 백그라운드 정리, 바로 쓸 수 있는 검색이 저장 계층 운영보다 중요할 때 더 좋습니다.
