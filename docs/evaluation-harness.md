# Competition skill evaluation harness

The current validation proves structure, not automatic skill selection or output quality. Use this harness to measure both before calling the suite reliable.

## A. Routing suite

For each prompt record expected owner/mode, actual selected skill, extra skills loaded, and pass/fail. Include paraphrases, terse Korean, English, ambiguous requests and negative controls.

Minimum cases:

1. `이 공모전 분석해줘` → analyze only.
2. `역대 수상작 뜯어봐` → analyze / winner protocol.
3. `문제부터 새로 캐자` → planning / problem mining.
4. `기존 아이디어 차별화 검증` → planning / whitespace, not full workflow.
5. `논문 특허 통계 근거 싹 검증` → evidence.
6. `기능명세서만 만들어줘` → feature spec only.
7. `3분 데모 동선 짜줘` → demo.
8. `질의응답만 준비` → presentation / Q&A only.
9. `악질심사` → review / adversarial.
10. `이 피드백 반영해서 수상최적화` with baseline/review → refinement.
11. `A대회 B대회 뭐가 더 꿀통?` → opportunity ranking.
12. `전체적으로 제출까지 진행` → router.
13. `정책 아이디어 공모전 기능명세 만들어` → clarify/requested spec without forcing app build.
14. unrelated coding request → no competition skill.

Measure owner accuracy, unnecessary-load rate and missed-required-protocol rate.

## B. Scenario quality suite

Maintain at least five fixtures: idea/policy contest, AI/data competition, 24–48h hackathon, capstone, and multi-track sponsor event. Each fixture includes official notice/rubric, limited public winner evidence, a deliberately flawed proposal, evidence register and implementation truth.

Score outputs on:

- official-rule fidelity;
- unsupported-claim rate;
- criterion→proof traceability;
- correct plan/mockup/implemented labels;
- differentiation quality against nearest alternative;
- demo observability and recovery;
- time-poor recall accuracy;
- issue precision and smallest-remedy quality;
- scope/complexity regressions;
- token/context cost.

## C. Adversarial fixtures

Inject traps: stale FAQ, contradictory source, fake-looking secondary statistic, unavailable dataset, sponsor API that is optional, copied winner wording, impressive but irrelevant feature, unsupported impact number, prerecorded demo mislabeled live, and a last-minute rubric correction. The suite should surface the trap rather than optimize around it.

## D. Ablation

Compare at minimum:

- baseline Core suite;
- + shared contracts;
- + judging-environment protocol;
- + communication-reality audit;
- + magic-moment-first hackathon branch;
- full v2.

Use identical fixtures and blind the evaluator to configuration names where possible. Keep changes only when gains reproduce without material token/context or feasibility regression.

## E. Release gate

Do not claim automatic routing reliability until the routing suite has been executed in the target Codex environment. Do not claim competition-performance improvement from author walkthroughs alone. Release notes must distinguish structural validation, simulated fixture performance, real user outcomes and actual awards.