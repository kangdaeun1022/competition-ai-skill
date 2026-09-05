# Competition Winning Skill Suite

공식 근거·문제 정의·실행가능성을 보존하면서 공모전 제출물을 발전시키는 **Core 9 + Optional 2** Codex 스킬입니다. 사용자 의도가 달라지는 지점을 독립 스킬로 나누고 세부 분석은 필요할 때만 읽는 references 프로토콜로 구성했습니다.

## 설치와 호출

Core 9 폴더를 Codex 스킬 폴더(기본 ~/.codex/skills/)에 설치하고 새 작업에서 사용하세요. 선택형은 필요할 때 추가합니다. 이 저장소 변경만으로 현재 Codex에 자동 설치되지는 않습니다. 자연어 별칭은 의도 라우팅 안내이며 확정 호출은 아래 내부 식별자를 사용합니다.

| 구분 | 내부 식별자 | 별칭 / 책임 |
| --- | --- | --- |
| Core 1 | $run-competition-winning-workflow | 공모전 — 전체 진행 |
| Core 2 | $analyze-competition-deeply | 공모전분석, 수상작역설계 — 공식 기준·주최기관·수상작·경쟁자 패턴 |
| Core 3 | $plan-competition-ideas | 공모전기획, 문제채굴, 차별화검증 — 문제·후보·AI fit·선행기술·MVP |
| Core 4 | $build-competition-evidence-pack | 공모전딥리서치, 근거자료집 — 논문·통계·특허·뉴스·데이터 검증 |
| Core 5 | $build-competition-feature-spec | 기능명세서, 공모전기능명세 — 서비스 흐름·상태·인수조건 |
| Core 6 | $engineer-competition-demo | 데모설계 — magic moment·결정 경로·복구·리허설 |
| Core 7 | $prepare-competition-presentation | IR덱, 발표설계, 질의응답 — 덱·대본·압박 Q&A |
| Core 8 | $review-competition-proposals | 공모전검토, 악질심사 — 공식 심사·공격 모드·최종 파일 감사 |
| Core 9 | $self-refine-with-overfit-guard | 수상최적화 — 버전 전이·검증·과적합 방지 |
| Optional | $map-competition-materials | 자료관계분석 — 많은 자료의 claim↔evidence 관계 |
| Optional | $prepare-design-brief | 디자인제안서 — 요청된 디자이너 전달 |

Core는 역량 구분입니다. 정책 공모전에 앱 기능명세를 강제하거나 Q&A 요청에 전체 덱을 다시 만들지 않습니다. 공식 산출물 요구에 따라 필요한 단계만 실행합니다.

## 전체 흐름

공식 Source Lock → 분석 → 기획 → Evidence Deep Research → MVP/기능명세 → Demo → Presentation/Q&A → Independent Review(Adversarial 포함) → Self-refine → 독립 validation과 회귀 검사 → 최종 Holdout → Q&A 보완/제출 QA → Submission Freeze.

반복 중에는 Review로 돌아가 변경한 버전을 검사합니다. 아이디어·정책, AI·데이터, 해커톤, 캡스톤별 우선순위는 라우터에 있으며 공식 배점이 항상 우선합니다. 자료관계분석은 자료가 많을 때, 디자인 전달은 요청 시 선택합니다.

## 내부 프로토콜

- 분석: winner-reverse-engineering, rubric-decoding, competitor-archetypes, organizer-intent
- 기획: problem-mining, competitive-whitespace, novelty-and-prior-art, ai-fit-gate, collapse-conditions
- 리뷰: official-rubric-review, adversarial-judge-pass, evidence-attack, system-operation-attack, submission-qa
- 발표: judge-first-deck, hostile-qa

모든 프로토콜은 소유 스킬의 references/ 아래에 있고 SKILL.md에 읽는 조건이 있습니다. 독립 스킬로 중복 설치하지 않습니다.

## 과적합 방지

원본 baseline과 best passing version을 별도로 보존합니다. 후보 수정은 공식 기준 관련성, regression, complexity budget, evidence drift, scope drift, demoability, single-judge overfit 검사를 통과해야 합니다. v8의 차별성이 높아져도 설명력·구현성이 하락하면 v8을 거절하고 v7을 유지합니다.

심사는 8개 관점과 2개 블라인드 풀, arbiter 구조입니다. 독립성은 격리된 평가 문맥 또는 별도 사람 심사자가 있어야 성립합니다. 한 대화에서 역할만 바꾼 결과는 비독립 비평으로 표시하며 holdout 통과로 인정하지 않습니다.

반복용 validation과 최종 holdout을 구분합니다. 피드백이 공개된 holdout은 소진 처리하고 다음 반복에 재사용해도 독립 검증으로 세지 않습니다.

기본 최대 40 evaluation opportunities, 3개 연속 무개선 후보에서 조기 종료를 검토합니다. 한 심사자가 한 버전을 평가하면 1회이며 8개 심사 평가는 8회입니다. 사용자가 500회를 지정해도 상한일 뿐입니다. 최종 holdout 기회를 먼저 예약하고, 개선 재현 실패·예산/리허설 보호 한도 도달 시 멈춥니다. 중대 결함이 남으면 NOT READY로 끝납니다.

## 기존 구조에서 이전

기존 독립 식별자 6개는 내부 프로토콜로 흡수했습니다.

| 기존 식별자 | 새 호출 |
| --- | --- |
| reverse-engineer-winning-entries | analyze-competition-deeply / 수상작역설계 |
| mine-high-value-problems | plan-competition-ideas / 문제채굴 |
| map-competitive-whitespace | plan-competition-ideas / 차별화검증 |
| simulate-adversarial-judges | review-competition-proposals / 악질심사 |
| architect-judge-first-deck | prepare-competition-presentation / IR덱 |
| prepare-hostile-qa | prepare-competition-presentation / 질의응답 |

이미 이전 버전을 설치했다면 해당 6개 폴더를 백업 후 스킬 검색 경로 밖으로 옮기고 새 구조를 설치하세요. 함께 남기면 이전 트리거가 계속 발견될 수 있습니다. 현재 변경은 저장소에만 적용되며 개인 설치 폴더를 자동으로 수정하지 않습니다.

## 사용 예

> 공모전: 첨부 공고·평가표와 현재 MVP를 기준으로 진행해줘. 기존 문제와 범위를 보존하고, 결정적인 주장부터 근거를 검증해줘.

> 악질심사: 이 버전에 대해 독립 심사와 중재 결과를 만들어줘. 파일 위치와 근거가 있는 결함부터 알려줘.

> 수상최적화: best version을 보존하면서 피드백을 반영해줘. 개선이 독립 검증에서 재현되지 않으면 멈추고, 최종 holdout은 분리해줘.

## 검증과 출처

검증은 [구조 및 시나리오 점검 기록](docs/validation.md)에 기록합니다. 형식 검증은 실제 공모전 성과나 자동 호출 정확도를 보장하지 않습니다.

[competition-ai-skill-suite](https://github.com/Suya020504/competition-ai-skill-suite)의 사용자 의도별 구조와 근거·정확성·정합성 원칙을 참고했습니다. 이 저장소의 신규 스킬과 프로토콜은 자체 작성했으며 upstream의 실행 스크립트나 문서 출력 도구를 포함하지 않습니다.
