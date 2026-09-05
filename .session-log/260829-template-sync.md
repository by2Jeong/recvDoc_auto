# 2026-08-29

session-id: 1730523e-a005-46b6-bb3e-6d398976a00e

1. template-repository 최근 스킬/에이전트/AGENTS.md 정책 동기화
   - AGENTS.md가 없던 상태(CLAUDE.md만 존재, 목적/목표 placeholder)라 신규 작성했다.
     목적/목표는 여전히 placeholder로 남겨둠 — 사용자가 채워야 함.
   - skill rename(prd-writer/srs-writer -> by-*), 신규 skill(by-adr-writer, by-mermaid-flowchart),
     .claude/agents 6종 추가.
   - `.codex/skills/prd-writer/SKILL.md`에 이 세션 시작 전부터 있던 미커밋 수정은 건드리지 않았다.
   - 반영: `AGENTS.md`(신규), `CLAUDE.md`, `.claude/agents/`, `.claude/skills/` (커밋 78aa98a)
