# 어떤 Second Brain으로 시작해야 할까?

이 페이지는 서로 배타적인 제품 분류가 아니라 세컨드 브레인 생애주기를 기준으로 구성되어 있습니다. 지금 가장 막히는 생애주기 빈칸부터 시작하세요: 수집, 정리, 발전, 활용, 관리. 두 경로가 모두 적용된다면 더 앞쪽 생애주기 빈칸을 먼저 해결한 뒤, [Solution Layers](solution-layers.md)에서 앱, local workspace, agent memory layer, substrate, platform baseline 중 어떤 종류를 채택하는지 확인하세요.

## 흩어진 맥락이 아직 수집되지 않는다면

[Membase](../solutions/membase.md), [OpenHuman](../solutions/openhuman.md), [Supermemory](../solutions/supermemory.md), [Hyperspell](../solutions/hyperspell.md), [Khoj](../solutions/khoj.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md)부터 보세요.

- Membase는 AI chat과 연결된 source를 local collector나 memory infrastructure 없이 Memory와 Wiki로 만들고 싶을 때 운영 부담이 낮은 hosted path입니다.
- OpenHuman은 자동 앱 수집이 있는 제품화된 local-first desktop AI assistant를 원할 때 강합니다.
- Supermemory와 Hyperspell은 수집된 맥락이 AI workflow, 제품, agent-facing API로 들어가야 할 때 유용합니다.
- Khoj는 파일, 노트, 문서, 웹 페이지가 주요 source일 때 더 잘 맞습니다.
- obsidian-wiki는 coding-agent history까지 source로 삼아 hosted connector layer 대신 agent가 함께 유지하는 Obsidian vault를 만들 때 더 강합니다.
- Obsidian/Logseq는 사람이 소유하는 local note가 source of truth일 때 강하지만, AI capture는 plugin, import, custom bridge에 의존합니다.

유용한 맥락이 아직 여러 도구에 흩어져 있는 것이 첫 문제라면 이 경로를 선택하세요.

## 원본 맥락을 오래 쓸 지식으로 정리해야 한다면

[Membase](../solutions/membase.md), [GBrain](../solutions/gbrain.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md), [Mnemosyne](../solutions/mnemosyne.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md), [Honcho](../solutions/honcho.md), [Zep/Graphiti](../solutions/zep-graphiti.md), [Cognee](../solutions/cognee.md)부터 보세요.

- Membase는 수집된 맥락을 Memory와 Wiki로 정리하고, Memory용 graph + vector retrieval과 dashboard chat까지 쓰고 싶을 때 부담이 낮은 hosted option입니다.
- GBrain은 self-hosted second brain을 위한 deterministic Markdown/page/link/timeline model과 source-scoped OAuth 경로를 제공하지만 stack 운영은 사용자가 맡습니다.
- obsidian-wiki는 여러 coding agent가 source와 conversation history를 provenance, delta tracking, graph-aware query, maintenance tool이 있는 하나의 Obsidian vault로 compile하도록 하는 shared skill workflow를 제공합니다.
- Hermes Agent + LLM Wiki는 schema, index, log, wikilink, provenance, lint 규칙이 있는 읽을 수 있는 Markdown wiki를 제공하지만 wiki 관리 규율은 사용자가 운영해야 합니다.
- Mnemosyne는 local SQLite-backed agent memory layer 안에서 memory tier, memory bank, hybrid retrieval, temporal triple을 제공합니다.
- taOSmd는 모든 conversation turn을 append-only archive에 verbatim으로 저장한 뒤, vector search, temporal knowledge graph, librarian layer를 얹어 low-end hardware에서 offline으로 실행합니다.
- Vestige는 prediction-error 단계에서 중복 record를 merge하고 모순 record를 supersede하며, local SQLite 위에 association을 가진 memory graph를 유지하는 coding agent용 단일 Rust binary입니다.
- Honcho는 stateful agent가 peer representation, conclusion, session context, 사용자 또는 agent modeling을 필요로 할 때 강합니다.
- Zep/Graphiti와 Cognee는 애플리케이션을 위한 graph 또는 knowledge memory substrate로 보는 편이 맞습니다.

관계, 엔티티, 사실, page, link, 시간이 가장 부족한 조각이라면 이 경로를 선택하세요.

## Memory가 시간이 지나며 발전해야 한다면

[Membase](../solutions/membase.md), [GBrain](../solutions/gbrain.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Hyperspell](../solutions/hyperspell.md), [Honcho](../solutions/honcho.md), [Hindsight](../solutions/hindsight.md), [Mnemosyne](../solutions/mnemosyne.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md), [Zep/Graphiti](../solutions/zep-graphiti.md), [Cognee](../solutions/cognee.md)부터 보세요.

이 선택지들은 원본 노트를 저장하는 데서 끝나지 않습니다. 제품이 관리하는 digesting, graph memory update, background reasoning, procedural memory extraction, automatic forgetting, dream/autopilot job, memory-bank consolidation, temporal graph update, graph processing workflow, 또는 agent-operated deduplication과 maintenance를 통해 수집 이후 memory가 개선되도록 돕습니다. Vestige는 FSRS-6 decay, prediction-error gated write, consolidation/dream maintenance, dedup, reversible active forgetting 때문에 이 그룹에 포함됩니다.

memory가 낡거나 중복되거나 서로 연결되지 않는 것이 문제라면 이 경로를 선택하세요.

## AI 도구와 workflow 안에서 맥락이 쓰여야 한다면

[Membase](../solutions/membase.md), [Supermemory](../solutions/supermemory.md), [Hyperspell](../solutions/hyperspell.md), [Honcho](../solutions/honcho.md), [Hindsight](../solutions/hindsight.md), [Mnemosyne](../solutions/mnemosyne.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [Mem0/OpenMemory](../solutions/mem0-openmemory.md), [Claude Projects/Claude Code](../solutions/claude-projects-code.md)부터 보세요.

- Membase는 MCP infrastructure를 먼저 운영하지 않아도 정리된 지식을 dashboard chat과 연결된 AI workflow에서 쓸 수 있게 합니다.
- Supermemory, Hyperspell, Honcho, Hindsight, Mnemosyne, taOSmd, Vestige, Mem0/OpenMemory는 memory가 agent나 application architecture의 일부일 때 더 잘 맞습니다. Vestige는 similarity search와 별도의 backward causal-recall 경로를 함께 제공하는 coding agent용 MCP/CLI local memory입니다.
- obsidian-wiki는 여러 coding agent가 portable skill instruction을 통해 같은 local compiled knowledge를 읽고 써야 할 때 더 강합니다.
- Claude Projects/Claude Code는 작업이 이미 Claude 안에 있고 project-scoped context로 충분할 때 유용합니다.

MCP, API, SDK, plugin, dashboard chat, platform access처럼 memory를 실제 작업 중 활성화하는 경로가 필요하다면 이 경로를 선택하세요.

## Memory를 확인, 수정, 통제해야 한다면

[Membase](../solutions/membase.md), [GBrain](../solutions/gbrain.md), [obsidian-wiki](../solutions/obsidian-wiki.md), [taOSmd](../solutions/taosmd.md), [Vestige](../solutions/vestige.md), [Hermes Agent + LLM Wiki](../solutions/hermes-llm-wiki.md), [Obsidian/Logseq + AI bridge](../solutions/obsidian-logseq.md), [ChatGPT Memory](../solutions/chatgpt-memory.md), [Claude Projects/Claude Code](../solutions/claude-projects-code.md)부터 보세요.

- Membase는 hosted Memory/Wiki control과 낮은 운영 부담을 함께 원할 때 유용합니다.
- GBrain, obsidian-wiki, Hermes Agent + LLM Wiki, Obsidian/Logseq, taOSmd는 local file, inspectability, human review가 hosted convenience보다 중요할 때 더 강합니다.
- Vestige는 local SQLite 위에 get/edit, promote/demote, contradiction inspection, reversible active forgetting(`suppress`), content와 embedding purge를 제공하며 embedded 3D dashboard에서 graph를 탐색할 수 있습니다.
- ChatGPT Memory와 Claude Projects/Claude Code는 유용한 platform baseline이지만 visibility, export, retrieval control은 platform 범위에 묶입니다.

review, correction, deletion, provenance, ownership, permission, local/cloud control이 핵심 판단 기준이라면 이 경로를 선택하세요.

## 이미 하나의 AI Platform 안에서 일한다면

[ChatGPT Memory](../solutions/chatgpt-memory.md), [Claude Projects/Claude Code](../solutions/claude-projects-code.md), [NotebookLM](../solutions/notebooklm.md)부터 보세요.

이들은 유용한 기준선이지만 platform-bound입니다. 더 넓은 수집, 정리, 검색 계층과 함께 쓰지 않는 한 완전한 self-evolving second brain으로 보면 안 됩니다.
