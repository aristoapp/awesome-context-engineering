# 에이전트 활용과 쓰기 반영

## 이 기능 축의 의미

에이전트 활용과 쓰기 반영은 AI 도구가 작업 중 세컨드 브레인을 검색하고, 가져오고, 인용하고, 쓰고, 업데이트하고, 유지보수하는 방식을 정의합니다. 일부 시스템은 외부 에이전트를 연결하기 전에도 브레인에 질문할 수 있는 자체 채팅 화면을 제공합니다.

## 평가 질문

- 접근 방식이 MCP, API, SDK, CLI, 플러그인, 플랫폼 전용 도구 중 무엇으로 제공되는가?
- AI 도구가 결과를 다시 쓸 수 있는가?
- 접근 권한이 user, source, project, workspace별로 범위 지정되는가?
- 호스트 AI 도구가 실제로 memory surface를 사용했는지 검증할 수 있는가?

## 평가 기준

이 기능 축은 저장소가 설정되어 있는지가 아니라, 세컨드 브레인이 AI-assisted work 중 실제로 사용 가능한지를 판단하는 데 사용합니다. 외부 AI 도구가 문서화된 표면을 통해 memory를 읽고 쓸 수 있고, 호출 범위가 올바르며, 호스트가 작업 중 memory surface를 실제 호출했다는 근거를 보여줄 수 있을수록 높게 평가합니다.

솔루션별 비교는 [../comparisons/agent-access.md](../comparisons/agent-access.md)를 참고하세요.

## 출처

- [Membase MCP](https://docs.membase.so/features/membase-mcp)
- [Supermemory MCP](https://supermemory.ai/mcp/)
- [Hyperspell MCP overview](https://docs.hyperspell.com/advanced/mcp-overview)
- [Honcho MCP integration](https://honcho.dev/docs/v3/guides/integrations/mcp)
- [Mnemosyne docs](https://docs.mnemosyne.site/)
- [Mnemosyne Hermes integration](https://github.com/AxDSan/Mnemosyne/blob/main/docs/hermes-integration.md)
- [taOSmd repository](https://github.com/jaylfc/taosmd)
- [taOSmd v0.2.0 release](https://github.com/jaylfc/taosmd/releases/tag/v0.2.0)
- [Vestige repository](https://github.com/samvallad33/vestige)
- [Mem0 MCP](https://docs.mem0.ai/platform/mem0-mcp)
- [Cognee MCP overview](https://docs.cognee.ai/cognee-mcp/mcp-overview)
