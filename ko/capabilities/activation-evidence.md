# 활용 증거

## 이 기능 축의 의미

활용 증거는 검색된 memory가 사람이나 AI workflow에 실제로 영향을 줬는지 증명할 수 있는지를 봅니다. 검색/활용과 관리 사이에 있는 축입니다. retrieval은 관련 맥락을 반환할 수 있지만, 활용 증거는 어떤 맥락이 로드, 인용, 승격, 거절, 실제 작업에 반영됐는지를 보여줍니다.

이 축은 모두 memory, RAG, MCP, agent access를 주장하는 시스템을 비교할 때 유용합니다. 질문은 단순히 "agent가 memory를 query할 수 있는가?"가 아니라 "사용자가 어떤 context가 task로 넘어갔고, agent가 그것을 안전하게 의존했는지 감사할 수 있는가?"입니다.

## 평가 질문

- 특정 task나 session에서 어떤 memory, note, file, fact, graph node가 검색됐는지 보여줄 수 있는가?
- candidate retrieval과 AI 도구에 실제로 주입, 열람, 인용, 활용된 context를 구분하는가?
- 사용자가 activated context의 freshness, source, scope, permission signal을 볼 수 있는가?
- context를 stale, refused, out of scope, unsafe로 표시할 수 있는가?
- 새로운 agent가 current decision, evidence, rejected option, stale risk, next safe action을 이해할 수 있는 handoff artifact가 있는가?
- AI 도구가 write-back할 수 있다면 어떤 source나 action 때문에 memory가 승격, 정정, 삭제됐는지 확인할 수 있는가?

## 실용적인 활용 테스트

vendor의 내부 ranking logic을 몰라도 작은 평가를 할 수 있습니다.

1. source가 있는 decision 하나, rejected option 하나, stale 또는 superseded note 하나를 준비합니다.
2. 세컨드 브레인에 연결된 깨끗한 AI-tool session을 시작합니다.
3. current decision, source evidence, rejected option, stale risk, next safe action을 요청합니다.
4. 답변이 polished summary에서 추측하지 않고 activated context를 인용하며 stale item을 올바르게 표시하는지 확인합니다.
5. agent가 작업을 수행한다면 retrieved context가 실제로 인용, 열람, write-back, action에 반영됐는지 확인합니다.

이 테스트를 통과하기 위해 private memory text를 log에 모두 노출할 필요는 없습니다. source ID, hash, timestamp, scope, 짧은 reason class만으로도 audit surface를 만들 수 있습니다.

## 솔루션 매트릭스

| 솔루션 | 지원 라벨 | 채택 경로 | 주의점 |
|---|---|---|---|
| Membase | 부분 지원 | Memory/Wiki retrieval과 연결된 AI workflow가 어떤 context를 쓸 수 있는지 확인할 수 있는 기반을 만듭니다. | 특정 workflow가 per-session retrieved-vs-used evidence를 노출하는지는 확인이 필요합니다. |
| GBrain | 부분 지원 | citation, conflict, gap analysis가 있는 CLI/MCP workflow가 activation check를 도울 수 있습니다. | per-session acted-on evidence는 hands-on 검증이 필요합니다. |
| Hermes Agent + LLM Wiki | 연동 | local Markdown wiki file이 source inspection과 handoff artifact 감사를 쉽게 만듭니다. | 활용 증거는 skill 동작과 사용자의 운영 규칙에 의존합니다. |
| Supermemory | 부분 지원 | MCP/API retrieval이 source-backed memory를 agent에 노출할 수 있습니다. | app owner가 어떤 retrieved item이 실제로 사용됐는지 기록해야 합니다. |
| Hyperspell | 부분 지원 | MCP search/get tool과 metadata filter가 context activation input을 제공할 수 있습니다. | host workflow가 retrieval을 넘어 usage를 기록하는지는 확인해야 합니다. |
| Honcho | 부분 지원 | session과 peer context API가 agent에게 어떤 context가 있었는지 설명하는 데 도움을 줄 수 있습니다. | acted-on evidence를 남기는지는 application integration에 달려 있습니다. |
| Mnemosyne | 부분 지원 | MCP, CLI, Hermes tool call을 통해 workflow에서 recall 또는 memory tool이 실행됐음을 보여줄 수 있습니다. | agent log가 retrieved memory를 decision, citation, write-back과 연결해야 합니다. |
| taOSmd | 부분 지원 | Append-only archive, pending-review list, local dashboard가 어떤 turn과 fact가 저장되고 검색 가능한지 보여줍니다. | agent log가 retrieved memory를 decision, citation, write-back과 연결해야 합니다. |
| Vestige | 부분 지원 | MCP tool call과 local 3D dashboard가 어떤 memory가 저장, 검색, 변경됐는지 보여주며 `recall`은 활용한 memory를 반환합니다. | agent log가 retrieved memory를 task의 decision, citation, write-back과 연결해야 합니다. |
| Mem0/OpenMemory | 부분 지원 | user/run-scoped memory search가 activation trace를 도울 수 있습니다. | grounding과 acted-on proof는 보통 app level 책임입니다. |
| Zep/Graphiti | 부분 지원 | temporal graph fact와 episode가 task evidence를 위한 source structure를 제공합니다. | application이 graph retrieval을 action log와 연결해야 합니다. |
| Cognee | 부분 지원 | knowledge graph recall tool이 agent에 structured context를 반환할 수 있습니다. | workflow별 host-level usage evidence 검증이 필요합니다. |
| Obsidian/Logseq + AI bridge | 연동 | local note, backlink, file history가 inspectable activation source가 됩니다. | bridge가 무엇을 로드하고 사용했는지 기록해야 합니다. |
| ChatGPT Memory | 미확인 | platform-native memory가 session을 personalize할 수 있습니다. | per-memory retrieval과 acted-on evidence는 platform-controlled입니다. |
| Claude Projects/Claude Code | 부분 지원 | project knowledge, file, skill, tool log가 context activation의 일부를 보여줄 수 있습니다. | loaded context와 acted-on context를 구분하려면 custom receipt나 log가 필요할 수 있습니다. |
| NotebookLM | 내장 | source-grounded answer와 citation이 bounded notebook 안에서 활용 증거를 보여줍니다. | 넓은 live workflow memory가 아니라 notebook source set에 제한됩니다. |

## 메모

활용 증거는 완벽한 observability와 다릅니다. 실용적인 세컨드 브레인은 privacy-safe receipt만으로 시작할 수 있습니다. 예를 들어 context ID, source reference, freshness, task/session ID, action taken, skipped/refused reason 정도면 handoff와 workflow automation에서 브레인을 신뢰할 수 있는지 판단하는 데 충분한 경우가 많습니다.

## 출처

- [에이전트 활용/쓰기 반영](agent-access.md)
- [검색과 활용](retrieval-grounding.md)
- [프라이버시와 통제권](privacy-control.md)
- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [GBrain solution profile](../solutions/gbrain.md)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)
