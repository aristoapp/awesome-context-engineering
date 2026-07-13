# 지식 정리

## 이 기능 축의 의미

지식 정리는 원본 맥락을 요약, 엔티티, 링크, 태그, 스키마, 그래프 엣지, 사실, 타임라인, wiki page처럼 오래 쓰고 재사용할 수 있는 지식으로 바꾸는 능력입니다.

## 평가 질문

- 정리가 자동으로 일어나는가, 아니면 명시적인 검토를 통해 일어나는가?
- 관계 추출은 규칙 기반, 의미 기반, LLM 추론 중 무엇인가?
- 사용자가 결과를 확인하고 정정할 수 있는가?
- 원본 데이터와 정리된 지식을 분리하는가?

## 솔루션 매트릭스

| 솔루션 | 지원 수준 | 도입 방식 | 주의할 점 |
|---|---|---|---|
| Membase | 내장 | Memory graph 추출, 연결된 Wiki 문서, collection. | Memory 검색에는 vector search도 사용되며 내부 제품 동작은 Membase가 관리합니다. |
| OpenHuman | 내장 | Memory Tree, 로컬 SQLite 지식 베이스, Markdown vault, 토큰 압축, 계층형 요약 트리, collapse flow. | 정확한 통합 품질은 테스트해야 합니다. |
| GBrain | 내장 | schema pack, `gbrain-base-v2`, schema detect/suggest/review flow, page type 추론, 자동 링크, 타임라인/사실 추출, take. | 구조화된 Markdown, 활성 스키마 선택, 검토가 있을수록 품질이 좋아집니다. |
| Hermes Agent + LLM Wiki | 내장 | schema, index, log, raw source, entity page, concept page, comparison page, query page, frontmatter, tag, wikilink, confidence, contradiction marker를 갖춘 에이전트 유지보수형 Markdown wiki. | 정리 품질은 에이전트가 skill을 따르는 정도와 사용자의 schema 관리 규율에 달려 있습니다. |
| Supermemory | 내장 | 처리 파이프라인, 사실 기반 graph memory, 관계 추적, 메타데이터/필터링. | 정확한 그래프 의미는 용도별로 확인해야 합니다. |
| Hyperspell | 내장 | memory, 연결된 data source, metadata filter, collection, structured resource data, LLM-ready summary, context graph claim, trace에서 추출한 procedural memory. | app owner가 taxonomy, metadata, review UI, safe recall boundary를 설계해야 합니다. |
| Honcho | 내장 | workspace, peer, session, message, conclusion, representation, peer card, session context. | 최종 사용자용 organization과 review UI는 통합 구현에 달려 있습니다. |
| Mnemosyne | 내장 | Working memory, episodic memory, scratchpad, memory bank, temporal graph-style fact용 TripleStore. | Organization 품질은 memory scope 설계, embedding 설정, agent write behavior에 달려 있습니다. |
| taOSmd | 내장 | Append-only archive, vector index, temporal knowledge graph, librarian layer가 raw turn을 retrievable structure로 바꿉니다. | Organization 품질은 local extraction model, embedding 설정, agent write behavior에 달려 있습니다. |
| Vestige | 내장 | Prediction-error gating이 ingest 때 중복 write를 merge하고 모순 write를 supersede합니다. association, synaptic tagging, per-project code memory를 가진 memory graph가 local SQLite + FTS5 + vector index 위에 구조를 더합니다. | Organization 품질은 local embedding model, tagging, agent write behavior에 달려 있습니다. |
| Mem0/OpenMemory | 내장 | 계층화된 memory 유형과 검색/승격 모델. | 앱은 범위와 메타데이터를 신중히 선택해야 합니다. |
| Zep/Graphiti | 내장 | entity node, entity edge, episodic node, fact, summary. | temporal graph 앱에는 강하지만 no-code PKM은 아닙니다. |
| Cognee | 내장 | knowledge graph memory 도구와 처리. | 그래프 품질은 수집과 처리 방식에 의존합니다. |
| Khoj | 내장 | 개인 파일/노트에 대한 인덱싱과 검색. | graph memory system보다 스키마 중심성은 약합니다. |
| Obsidian/Logseq + AI bridge | 부분 지원 | 태그, 링크, 속성, 블록, 플러그인. | AI 기반 정리는 bridge에 의존합니다. |
| ChatGPT Memory | 내장 | 플랫폼이 관리하는 저장 memory와 대화 히스토리 참조. | 개발자가 정리 방식을 직접 운영할 수는 없습니다. |
| Claude Projects/Claude Code | 내장 | 프로젝트 지식, 지침, 플랫폼 RAG 동작. | 구조는 Claude 프로젝트 맥락 안에 묶입니다. |
| NotebookLM | 내장 | 자료가 충분할 때 출처 요약, 라벨/카테고리, 생성된 결과물. | 제한된 notebook에는 강하지만 살아 있는 memory graph는 아닙니다. |

## 출처

- [Membase overview](https://docs.membase.so/)
- [How Membase works](https://docs.membase.so/core-concepts/how-membase-works)
- [Hermes LLM Wiki skill](https://github.com/NousResearch/hermes-agent/tree/main/skills/research/llm-wiki)
- [Hyperspell core concepts](https://docs.hyperspell.com/core/concepts)
- [Hyperspell procedural memory](https://docs.hyperspell.com/usage/procedural-memory)
- [Honcho overview](https://honcho.dev/docs/v3/documentation/introduction/overview)
- [Mnemosyne docs](https://docs.mnemosyne.site/)
- [Mnemosyne repository](https://github.com/AxDSan/Mnemosyne)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Zep graph documentation](https://help.getzep.com/v2/understanding-the-graph)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
