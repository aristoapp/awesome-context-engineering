# obsidian-wiki

## 개요

- 웹사이트 / 문서: https://github.com/Ar9av/obsidian-wiki
- Package: https://pypi.org/project/obsidian-wiki/
- 회사 / 관리자: Ar9av와 contributors
- 상태: 활발한 public repository와 배포된 Python package
- 오픈소스: 예, MIT License
- 배포: 설치된 agent skill과 선택적 local CLI utility로 운영하는 local Markdown/Obsidian vault
- 주요 사용자: 하나 이상의 coding agent를 사용하며 확인 가능하고 이식성 있는 세컨드 브레인을 원하는 사용자
- 세컨드 브레인 역할: Obsidian을 위한 agent-agnostic local knowledge-compilation framework
- 마지막 검토: 2026-07-11
- 검토 근거: 공식 repository README, package metadata, bundled skill, license

## 한 줄 요약

obsidian-wiki는 여러 coding agent가 source를 ingest하고, durable knowledge를 하나의 Obsidian vault에 병합하고, 질의하고, 시간에 따라 구조를 유지할 수 있게 하는 공통 Markdown skill 모음을 설치합니다.

## 세컨드 브레인 적합도

obsidian-wiki는 hosted memory service보다 local workspace와 운영 패턴에 가깝습니다. Skill은 지원 agent가 문서, URL, 대화 history, project context, rough note를 필수 frontmatter, source provenance, index, activity log, ingest source를 추적하는 manifest가 있는 상호 연결된 Markdown page로 compile하도록 안내합니다.

일반적인 Obsidian AI bridge와 달리 repository 자체가 setup, ingest, agent-history import, delta-aware project update, query, capture, lint, deduplication, cross-linking, synthesis, dashboard, export, rebuild, daily maintenance로 이어지는 knowledge lifecycle을 제공합니다. 여러 agent client가 같은 vault를 사용할 수 있지만, model과 실행 품질은 skill을 수행하는 agent에 따라 달라집니다.

## 기능 평가

| 영역 | 평가 |
|---|---|
| 배포 / 소유권 | Local-first. Source of truth는 사용자가 선택한 Obsidian-compatible Markdown directory이며, configuration이 agent와 CLI를 해당 vault로 연결합니다. |
| 맥락 수집 | File, folder, URL, PDF, image, raw text, chat export와 Claude Code, Codex, Hermes, OpenClaw, Copilot CLI, Pi history용 skill workflow가 내장되어 있습니다. 넓은 SaaS OAuth 수집은 내장되어 있지 않습니다. |
| 지식 정리 | Category, frontmatter, summary, source tracking, wikilink, index/log/hot-cache file, controlled tag, project page, duplicate page를 피하기 위한 merge-in-place rule이 내장되어 있습니다. |
| Memory 발전 | 내장되어 있지만 agent가 운영합니다. Manifest는 delta ingest를 지원하고, maintenance skill은 update, lint, deduplication, cross-linking, synthesis, rebuild/restore, tag normalization, daily freshness check, hot-cache refresh를 다룹니다. 지속 관리형 service가 아니라 호출하거나 schedule할 때 실행됩니다. |
| 검색 / 활용 | Wiki query skill과 local CLI graph query가 내장되어 있습니다. Query workflow는 page를 선택적으로 읽기 전에 metadata와 graph candidate를 ranking하고, 근거 wiki page link와 함께 답을 반환합니다. |
| 에이전트 활용 / 쓰기 반영 | Claude Code, Codex, Cursor, Windsurf, Gemini CLI, Hermes, OpenClaw, Pi, Copilot CLI 및 instruction file을 읽는 agent가 portable skill과 filesystem access를 통해 사용합니다. 전용 MCP server나 hosted API는 필요하지 않습니다. |
| 개인 / 팀 범위 | 개인과 project에 강합니다. Named vault profile과 invocation별 routing으로 context를 분리합니다. Team sharing, concurrent edit, permission, approval workflow는 외부 filesystem, Git, Obsidian Sync 선택에 달려 있습니다. |
| 검토 / 정정 | File 수준 검토가 강합니다. 사용자는 Obsidian에서 Markdown을 직접 편집하고, provenance를 검토하고, 깨진 link/metadata를 lint하고, duplicate를 찾고, archive/rebuild 및 snapshot restore를 수행할 수 있습니다. Agent write를 막는 built-in approval UI는 없습니다. |
| 프라이버시 / 통제권 | Vault file은 local의 export 가능한 Markdown으로 남습니다. Model prompt, web read, embedding, sync, agent history의 privacy는 선택한 agent, model provider, optional QMD configuration, storage/sync setup에 달려 있습니다. |
| 설정 / 운영 | 중간. `pip install obsidian-wiki`와 `obsidian-wiki setup --vault ...`가 공통 skill과 configuration을 설치하지만, backup, sync, source review, agent run, maintenance cadence는 사용자가 운영합니다. |

## 강점

- 하나의 읽을 수 있는 Markdown vault를 여러 coding-agent client에서 사용할 수 있습니다.
- 검색을 넘어 ingest, merge, provenance, delta tracking, query, lint, deduplication, synthesis, export, rebuild까지 lifecycle을 다룹니다.
- Compile된 knowledge와 graph를 Obsidian에서 확인할 수 있습니다.
- 전용 history-ingest skill이 여러 coding agent의 과거 session을 정리할 수 있습니다.
- Named vault profile과 inline routing으로 default vault를 바꾸지 않고 여러 개인용 또는 업무용 brain을 지원합니다.
- MIT license이며 dependency가 가벼운 core package와 portable skill instruction을 제공합니다.

## 한계

- Skill을 실행하는 agent가 extraction, merge, file edit를 책임지므로 model capability와 instruction 준수에 따라 결과가 달라집니다.
- Built-in SaaS connector platform, 상시 ingestion service, 전용 memory API/MCP server가 없습니다.
- 자동 발전은 always-on managed consolidation loop가 아니라 maintenance command 또는 scheduler로 실행됩니다.
- Team permission, conflict resolution, review gate, shared-vault sync는 외부 영역입니다.
- Local vault 소유권이 선택한 model provider, browser, sync provider, optional search index 호출까지 private 또는 offline으로 만들지는 않습니다.
- Low-latency per-turn episodic memory보다 durable compiled knowledge에 최적화되어 있습니다.

## 잘 맞는 경우

- 여러 coding tool에서 하나의 portable knowledge base를 쓰고 싶은 multi-agent 사용자.
- Agent가 관리하는 knowledge를 Obsidian에서 편집하고 감사할 수 있게 유지하려는 사용자.
- 문서, project decision, agent conversation을 자주 정리하는 개발자와 연구자.
- Hosted memory service 대신 명시적 maintenance를 실행하거나 schedule할 의향이 있는 사용자.

## 잘 맞지 않는 경우

- One-click OAuth connector와 business app background capture를 원하는 사용자.
- Built-in RBAC, approval, concurrent editing, admin governance가 필요한 팀.
- Memory API 또는 SDK backend를 찾는 application 개발자.
- File이나 vault 관리 없이 보이지 않게 자동 동작하는 episodic memory를 원하는 사용자.

## 트레이드오프

obsidian-wiki는 hosted automation과 product-managed governance를 portability, inspectability, cross-agent reuse와 맞바꿉니다. Bare Obsidian vault보다 더 규율 있는 lifecycle을 제공하지만, agent 선택, maintenance cadence, sync, backup, 생성된 knowledge 검토는 사용자가 책임집니다.

## 공식 설정 / 평가 링크

- [Repository와 quick start](https://github.com/Ar9av/obsidian-wiki)
- [PyPI package](https://pypi.org/project/obsidian-wiki/)
- [Wiki setup skill](https://github.com/Ar9av/obsidian-wiki/blob/main/.skills/wiki-setup/SKILL.md)
- [Wiki ingest skill](https://github.com/Ar9av/obsidian-wiki/blob/main/.skills/wiki-ingest/SKILL.md)
- [Wiki query skill](https://github.com/Ar9av/obsidian-wiki/blob/main/.skills/wiki-query/SKILL.md)
- [Wiki lint skill](https://github.com/Ar9av/obsidian-wiki/blob/main/.skills/wiki-lint/SKILL.md)

## 출처

- [obsidian-wiki README](https://github.com/Ar9av/obsidian-wiki/blob/main/README.md)
- [Package metadata](https://github.com/Ar9av/obsidian-wiki/blob/main/pyproject.toml)
- [Bundled skills](https://github.com/Ar9av/obsidian-wiki/tree/main/.skills)
- [MIT License](https://github.com/Ar9av/obsidian-wiki/blob/main/LICENSE)
