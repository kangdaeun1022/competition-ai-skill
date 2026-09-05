---
name: prepare-hostile-qa
description: Prepare evidence-led answers to skeptical competition questions with intent, risky answer, 20-second response, support, follow-up attack, and 10-second rebuttal. Invoke for “질의응답”, hostile Q&A, panel questions, defense rehearsal, or presentation rebuttal requests.
metadata:
  short-description: 압박 질의응답 준비
---

# Prepare hostile Q&A

## Purpose

Prepare the team to answer difficult questions honestly, briefly, and with a concrete next proof. The aim is credible command of limits, not verbal victory or a claim that cannot survive follow-up.

## Build questions from real attack surfaces

Start with the official rubric, adversarial-judge findings, evidence gaps, demo dependencies, differentiation map, operational constraints, and implementation truth. Cover at least the relevant categories:

- eligibility and submission compliance;
- problem validity and stakeholder adoption;
- evidence quality, numbers, baseline, and causality;
- novelty, substitutes, prior art, patents/rights signals;
- technical feasibility, data access, AI necessity, privacy, safety, and failure modes;
- operating model, cost, scale, accountability, and timeline;
- demo reliability, claims versus implementation, and limitations.

Do not invent a hostile premise when a more specific, artifact-grounded question is available.

## Required answer card

Use this exact Korean-facing structure for every high-risk question:

```text
Q&A_CARD
- 질문:
- 질문 의도: 이 질문이 검증하려는 심사 기준 또는 위험
- 위험 답변: 과장, 회피, 근거 없는 숫자, 혹은 범위 이탈이 되는 답
- 20초 답변: 결론 → 가장 강한 근거 → 현재 한계/통제의 순서
- 근거: 출처·데모 결과·구현 위치·검증계획과 상태
- 후속공격: 심사위원이 합리적으로 이어 물을 가장 강한 질문
- 10초 재반박: 범위를 지키며 사실과 다음 증명을 말하는 짧은 답
```

The 20-second answer should state a direct answer first, then one strongest proof, then an honest boundary. The 10-second rebuttal should not introduce new unsupported evidence; it can say what is not yet proved and how the team will test it.

## Rehearse under constraints

- Assign an owner for every question and a backup speaker for core questions.
- Time answers aloud; remove throat-clearing, marketing language, and claims the speaker cannot locate in an artifact.
- Ask a reviewer to deliver follow-up attacks without showing the answer key.
- Log `question → response quality → unsupported phrase → repair → evidence owner`.
- When an answer exposes a real blocker, send it back to the evidence, demo, or refinement workflow rather than polishing the wording.

## Output

Return Q&A cards ordered by likelihood × damage, a one-page rapid-response sheet, answers that require evidence repair, and a final list of statements the team must not make. Preserve disagreement and uncertainty; never claim competitive uniqueness, live reliability, impact, or approval without support.
