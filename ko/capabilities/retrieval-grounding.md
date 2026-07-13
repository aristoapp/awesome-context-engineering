# 검색과 활용

## 이 기능 축의 의미

검색과 활용은 시스템이 관련 memory를 어떻게 찾는지, 출처 맥락을 보존할 수 있는지, 사람 또는 AI 도구가 실제 작업에서 그 맥락을 적용할 수 있는지를 다룹니다.

## 평가 질문

- 검색이 키워드 검색, 벡터 검색, 그래프 검색, RAG, hybrid model 중 무엇을 사용하는가?
- 검색 시 출처, 시각, 프로젝트, collection, 권한 신호가 제공되는가?
- 사용자 또는 AI 도구가 memory 뒤의 출처를 인용하거나 확인할 수 있는가?
- 최신 출처 데이터와 오래되었거나 가져왔거나 추론된 memory를 구분할 수 있는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 내장 | 출처/프로젝트/날짜 필터가 있는 Memory용 graph + vector hybrid RAG, collection 범위 지정이 있는 Wiki용 vector + keyword hybrid search. | 대시보드 채팅과 연결된 에이전트가 두 저장소를 모두 사용할 수 있습니다. 대상 계정에서 사용 가능한 정보원을 확인하세요. |
| OpenHuman | 내장 | 로컬 Memory Tree, Obsidian 호환 Markdown vault, memory graph, 맥락 압축. | 출처/근거 동작은 직접 검증이 필요합니다. |
| GBrain | 내장 | `search`는 저비용 hybrid retrieval, `query`는 필터가 있는 확장 hybrid retrieval, graph/link 신호, timeline/fact retrieval, `think`는 인용/충돌/누락 분석이 있는 종합 답변. | 품질은 동기화, 임베딩, 정리된 출처 구조, reranker/provider 설정에 의존합니다. |
| Hermes Agent + LLM Wiki | 내장 | skill이 `SCHEMA.md`, `index.md`, `log.md`로 orientation하고, file search, 관련 page 읽기, compiled wiki page 기반 답변 종합, 가치 있는 답변의 wiki 저장을 수행합니다. | 기본적으로 vector DB나 graph RAG engine은 아닙니다. 최신성은 wiki maintenance에 달려 있습니다. |
| Supermemory | 내장 | 추출된 memory와 문서 chunk를 함께 찾는 hybrid search, graph memory, project/container 범위 지정, 메타데이터, API 필터. | 커넥터와 프로젝트 범위를 신중히 설정해야 합니다. |
| Hyperspell | 내장 | indexed search, live search, multi-source query, metadata/date/resource filter, source weighting, LLM-ready summary, optional answer generation, MCP search/get tool. | indexed/live availability는 source에 따라 다릅니다. beta integration과 query behavior는 계정별로 검증해야 합니다. |
| Honcho | 내장 | hybrid search, context retrieval, peer/session representation, peer card, conclusion, natural-language context query. | source metadata와 citation UX는 app 또는 agent가 Honcho에 데이터를 쓰는 방식에 달려 있습니다. |
| Mnemosyne | 내장 | Hybrid recall이 vector similarity, SQLite FTS5, importance weighting을 결합하고, MCP, CLI, SDK, Hermes plugin surface가 memory를 검색할 수 있습니다. | Source grounding은 memory write 방식과 host agent가 retrieved context를 기록하는지에 달려 있습니다. |
| taOSmd | 내장 | Hybrid keyword/vector search, fusion, optional reranker, temporal knowledge graph, librarian을 사용하며 결과는 verbatim archived turn을 참조할 수 있습니다. | Grounding 품질은 local embedding/LLM model과 host agent가 retrieved context를 기록하는지에 달려 있습니다. |
| Vestige | 내장 | `recall`이 similarity search, cross-memory reasoning, contradiction detection을 Reciprocal Rank Fusion으로 결합하고 `backfill`은 별도의 backward entity-linked causal-recall 경로를 제공합니다. | Grounding 품질은 local embedding model과 host agent가 retrieved context를 기록하는지에 달려 있습니다. causal-recall benchmark는 maintainer가 공개한 결과입니다(profile 참고). |
| Mem0/OpenMemory | 내장 | user ID, run ID, metadata가 있는 layered memory search. | 앱 소유자가 grounding과 출처 메타데이터 품질을 정의합니다. |
| Zep/Graphiti | 내장 | temporal knowledge graph, fact, episode, Graph RAG. | 애플리케이션 데이터가 명시적으로 모델링될 때 가장 좋습니다. |
| Cognee | 내장 | knowledge graph memory와 recall 도구. | 검색 품질은 수집과 그래프 처리 모드에 의존합니다. |
| Khoj | 내장 | 파일/노트 위의 자연어 검색과 채팅. | 자료 Q&A에는 강하지만 여러 도구를 아우르는 넓은 세컨드 브레인 계층으로는 약합니다. |
| Obsidian/Logseq + AI bridge | 연동 | 로컬 검색, backlink, graph view, bridge가 제공하는 RAG/search. | grounding 품질은 선택한 bridge에 의존합니다. |
| ChatGPT Memory | 부분 지원 | 플랫폼 memory, 대화 히스토리 참조, 지원되는 Memory Sources. | 출처와 검색 내부 동작은 플랫폼이 통제하며 요금제/지역에 따라 달라집니다. |
| Claude Projects/Claude Code | 내장 | 프로젝트 지식 검색/RAG와 Claude 맥락 표면. | grounding은 Claude 맥락과 요금제 동작 안에 묶입니다. |
| NotebookLM | 내장 | 출처 기반 notebook 검색과 출처 선택. | 제한된 출처 묶음에는 강하지만 workflow 전반에 걸친 살아 있는 세컨드 브레인으로는 약합니다. |

## 출처

- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell manual integration](https://docs.hyperspell.com/core/integration)
- [Hyperspell MCP overview](https://docs.hyperspell.com/advanced/mcp-overview)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Mnemosyne docs](https://docs.mnemosyne.site/)
- [Mnemosyne configuration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/configuration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)
