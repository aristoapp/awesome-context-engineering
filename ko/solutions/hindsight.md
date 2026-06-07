# Hindsight

## 개요

- 웹사이트 / 문서: https://hindsight.vectorize.io/
- 회사 / 관리자: Vectorize
- 상태: hosted와 self-hosted 배포 경로가 있는 open-source project
- 오픈소스: 예, MIT 라이선스 repository
- 배포: Cloud, Docker, bare metal Python package, embedded Python server, local MCP server
- 주요 사용자: persistent memory API가 필요한 agent를 만드는 개발자
- 세컨드 브레인 역할: memory bank가 있는 agent memory API
- 마지막 검토: 2026-06-01

## 한 줄 요약

Hindsight는 memory bank에 맥락을 저장하고 retain, recall, reflect operation을 API, SDK, CLI, MCP surface로 노출하는 agent memory system입니다.

## 세컨드 브레인 적합도

Hindsight는 소비자용 note-taking interface보다 개발자가 운영하는 agent/application memory layer에 더 잘 맞습니다. 세컨드 브레인이 programmatic memory write, retrieval, consolidation, agent-facing tool access를 필요로 할 때 유용합니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | Cloud가 있으며 self-hosted 경로로 Docker, bare metal Python, embedded local server option이 문서화되어 있습니다. |
| 맥락 수집 | retain operation을 통한 API-driven capture. integration과 wrapper가 agent interaction을 연결할 수 있습니다. |
| 지식 정리 | memory bank, fact, observation, mental model, tag, document, bank configuration을 내장합니다. |
| Memory 발전 | observation consolidation과 mental model refresh workflow가 문서화되어 있습니다. |
| 검색 / 활용 | recall은 semantic, keyword, graph, temporal retrieval strategy를 결합하고, reflect는 memory를 사용해 답변을 생성합니다. |
| 에이전트 활용 / 쓰기 반영 | MCP server, HTTP API, Python client, TypeScript client, CLI, framework integration이 문서화되어 있습니다. |
| 개인 / 팀 범위 | memory bank가 context를 분리할 수 있습니다. 정확한 team governance 적합성은 배포별 확인이 필요합니다. |
| 검토 / 정정 | mental model과 directive management가 노출되어 있습니다. 완성형 user-facing correction workflow는 integration에 달려 있습니다. |
| 프라이버시 / 통제권 | self-hosting을 지원하지만 production 운영에는 database, model provider, service configuration 관리가 필요합니다. |
| 설정 / 운영 | 공식 quickstart가 있습니다. 실제 설정 시간과 production 부담은 Docker, embedded, cloud, external PostgreSQL 경로에 따라 달라집니다. |

## 강점

- retain, recall, reflect로 이어지는 memory API surface가 명확합니다.
- local MCP server가 agent client용 memory tool을 노출합니다.
- self-hosted deployment와 client SDK를 지원합니다.
- memory-bank model로 agent, user, task context를 분리할 수 있습니다.

## 한계

- 완성형 소비자 세컨드 브레인 앱이 아니라 개발자용 infrastructure입니다.
- managed cloud를 쓰지 않으면 service와 storage layer를 운영해야 합니다.
- benchmark performance나 enterprise use claim은 이 프로필의 평가 근거로 다루지 않았습니다.
- 이 프로필은 공식 문서와 repository page 기반이며, hands-on deployment report는 아닙니다.

## 잘 맞는 경우

- persistent memory를 API로 써야 하는 agent를 만드는 팀.
- agent workflow에 MCP-accessible long-term memory를 붙이고 싶은 개발자.
- user, agent, task별로 별도 memory bank가 필요한 애플리케이션.

## 잘 맞지 않는 경우

- ready-made personal knowledge UI를 원하는 사용자.
- memory infrastructure를 운영하거나 API를 통합하고 싶지 않은 팀.
- 제한된 문서 집합 위의 source-grounded notebook workflow만 필요한 경우.

## 트레이드오프

Hindsight는 개발자에게 여러 activation surface가 있는 structured memory layer를 제공하지만, 그 가치는 integration과 운영 작업을 동반합니다. 완성형 세컨드 브레인 제품보다 memory API가 핵심 요구일 때 Mem0/OpenMemory, Supermemory, Zep/Graphiti, Cognee와 비교하는 것이 적절합니다.

## 공식 설정 / 평가 링크

- 문서: https://hindsight.vectorize.io/
- Repository: https://github.com/vectorize-io/hindsight
- Installation: https://hindsight.vectorize.io/developer/installation
- Local MCP server: https://hindsight.vectorize.io/sdks/integrations/local-mcp
- API reference: https://hindsight.vectorize.io/api-reference

## 출처

- https://hindsight.vectorize.io/
- https://github.com/vectorize-io/hindsight
- https://hindsight.vectorize.io/developer/installation
- https://hindsight.vectorize.io/sdks/integrations/local-mcp
