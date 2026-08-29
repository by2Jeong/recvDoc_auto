---
name: by-adr-writer
author: JBY
description: >
  02-design 단계에서 되돌리기 비용이 큰 구조적 결정을 논의·확정하고 ADR(Architecture
  Decision Record)로 기록할 때 사용한다. ADR을 쓸지 말지 판단하는 기준, ADR 파일 형식,
  SAD/SDD에서 ADR을 참조하는 방식, 게이트가 무엇을 검사하는지가 이 스킬의 범위다.
  "ADR 쓸지 판단", "아키텍처 결정 기록", "이 결정 되돌리기 어려운가" 같은 상황에서
  반드시 이 Skill을 사용한다.
---

# Writing an ADR
(요약: ADR 작성 스킬)

## Flow
(요약: 논의 -> 결정 -> 기록 -> 반영 -> 참조, 전체 흐름)

```
discuss -> decide -> record in docs/adr/ADR-nnn.md -> reflect in SAD -> reference as [SAD-R###]
```

## Whether to write one

(요약: ADR은 선택 사항, 자명하면 만들지 않음)

An ADR is **optional**. Do not create one for a self-evident structure. The gate also passes
if no ADR exists. (요약: ADR 없어도 게이트는 통과함) If a decision cannot be made, do not
force an ADR — leave it as `[확인 필요: ...]` and ask the user instead. Never invent a
decision on your own. (요약: 결정 못 하면 억지로 만들지 말고 사용자에게 물을 것)

## Format and reference rules

(요약: 형식과 참조 규칙)

- At the top of the ADR file, write `대상: [SAD-R001]` to state which decision item it targets.
- In the SAD's `아키텍처 결정` section, point to it with `- 참조: ADR-nnn` — **number only**.
  Do not copy the details into the SAD. SAD/SDD always reference by number only, never
  duplicate the body. (요약: SAD는 번호만 참조, 본문 중복 금지)
- If `TBD`/`미정`/`결정 필요` remains inside an ADR, the gate blocks it.
  (요약: ADR에 미결 표시 남아있으면 게이트 막힘)

## What the gate actually checks

(요약: 게이트가 실제로 검사하는 범위)

**The gate only checks existence**: whether the referenced `ADR-nnn` file actually exists,
plus whether any `TBD` remains. (요약: 존재 여부 + TBD 잔존만 검사) It does not check
bidirectional links or orphan ADRs — even if an ADR is created and nobody references it, the
gate does not block on that (though that itself is a sign the ADR was not needed in the
first place). (요약: 고아 ADR은 검사 안 하지만, 애초에 불필요했다는 신호일 수 있음)
