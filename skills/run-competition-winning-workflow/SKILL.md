---
name: run-competition-winning-workflow
description: Route end-to-end competition work from official-notice lock through winning-entry analysis, problem discovery, differentiation, evidence, MVP, demo, deck, adversarial review, guarded refinement, holdout review, Q&A, and submission freeze. Invoke for “공모전” or broad requests to prepare, win, continue, or coordinate an idea, policy, AI/data, hackathon, or capstone competition.
metadata:
  short-description: 공모전 수상 워크플로 라우터
---

# Run the competition-winning workflow

## Purpose

Coordinate only the unfinished work required to make a credible, judge-ready submission. Treat the verified problem definition, evidence, implementation truth, and agreed scope as assets to protect—not raw material to replace with a larger feature list.

Interpret `공모전` as this router. Delegate focused requests to the listed specialist skill without forcing a full workflow.

| User expression | Specialist skill |
| --- | --- |
| `수상작역설계` | `$reverse-engineer-winning-entries` |
| `문제채굴` | `$mine-high-value-problems` |
| `차별화검증` | `$map-competitive-whitespace` |
| `악질심사` | `$simulate-adversarial-judges` |
| `수상최적화` | `$self-refine-with-overfit-guard` |
| `데모설계` | `$engineer-competition-demo` |
| `IR덱`, `발표설계` | `$architect-judge-first-deck` |
| `질의응답` | `$prepare-hostile-qa` |

## Start with the official lock

Before ideation or judging, create an **OFFICIAL_NOTICE_LOCK**. Read the original notice, corrections, FAQ, rubric, submission form, dates, eligibility, deliverable constraints, and official URLs. Extract:

- confirmed requirement, source, effective date, and consequence if missed;
- rubric item, points or stated priority, implied judge question, and evidence needed;
- ambiguity, the exact clarification needed, and whether it blocks work.

Do not replace official requirements with a summary article, an old notice, or a prior contest’s convention. Reopen only the affected work when an official correction changes a lock.

## Classify the competition and set provisional weights

Use the official rubric when available. Otherwise state that the following are provisional and get the user’s correction if the classification is consequential.

| Type | Provisional scorecard weights when no official score exists | Route emphasis | Avoid |
| --- | --- | --- | --- |
| Idea / policy | problem and stakeholder evidence 30 · policy/public fit 25 · operating feasibility 25 · persuasion 20 | validate the operating pathway before building a product; a policy scenario can replace a live app demo | treating a mockup as proof of policy impact |
| AI / data | problem/rubric fit 20 · data/AI necessity/safety 30 · evaluation and MVP proof 30 · adoption/governance 20 | run data access, non-AI alternative, evaluation, and human-oversight checks before feature work | unsupported accuracy claims or AI-for-AI’s-sake |
| Hackathon | working MVP and demo 35 · user value 25 · differentiation 15 · delivery feasibility 15 · presentation 10 | bring the magic moment and recovery plan forward; protect rehearsal time | broad architecture with no demoable core |
| Capstone | technical depth 30 · implementation evidence 30 · research/validation 20 · impact and communication 20 | strengthen architecture, reproducibility, technical contribution, and implementation evidence | presenting planned work as implemented |

Record an initial scorecard: `criterion → weight/source → current evidence → risk → smallest next proof`. Keep one **complexity budget** consisting of available time, people, data/permissions, and demo/rehearsal capacity.

## Minimum complete route

Run these stages in order, skipping a stage only when its required output already exists and remains valid:

1. Official notice lock.
2. `$reverse-engineer-winning-entries` to separate formal criteria, public winner patterns, hypotheses, and strategy.
3. `$mine-high-value-problems` to choose an evidence-backed, bounded problem.
4. Select one leading idea plus one genuinely different fallback; record collapse conditions.
5. `$map-competitive-whitespace` across current services, prior art, contest entries, and patents/rights where relevant.
6. Conduct decisive-claim evidence research before using effect, demand, feasibility, or novelty claims.
7. Define the smallest credible MVP and feature specification. Mark each item as implemented, partial, mockup, or plan.
8. `$engineer-competition-demo` and rehearse a deterministic proof path.
9. `$architect-judge-first-deck` from judge questions rather than a generic company narrative.
10. `$simulate-adversarial-judges` for independent attack surfaces.
11. `$self-refine-with-overfit-guard`; preserve a baseline and use holdout review before accepting changes.
12. Run the holdout judge named by the refinement gate, then `$prepare-hostile-qa`.
13. Freeze the submission: compliance, source links, filenames, format, implementation labels, demo fallback, and version are checked. No new features after freeze except a blocker, official-rule change, or evidence correction.

## Handoff contract

At each boundary, pass a compact record rather than silently revising earlier work:

```text
DECISION_HANDOFF
- locked facts and sources:
- official criterion affected:
- selected problem / intervention / excluded scope:
- claims with evidence status (verified | planned validation | unsupported):
- implementation truth (implemented | partial | mockup | plan):
- current scorecard and highest risks:
- complexity budget remaining:
- changes since the prior baseline and reason:
- reopen trigger:
```

## Non-negotiable safeguards

- Do not infer judge personalities, hidden scoring, or award probability from public winner lists.
- Keep official facts, observed patterns, analytic hypotheses, and team strategy visibly separate.
- Treat lack of search results as `searched within scope; not confirmed`, never as proof of novelty or patent freedom.
- Add a feature, slide, metric, or claim only if it improves an official criterion **and** has evidence, a named owner, a feasible deadline, and a demo or operational consequence. Otherwise defer or remove it.
- If a late finding contradicts a prior assumption, mark the impacted claim/feature `revalidation required`; do not silently update the narrative.
- Ask at most three questions at a time only when the answer materially changes a route. Otherwise state an assumption and make useful progress.

## Output

Return the current stage, official locks, type-specific scorecard, completed and skipped stages with reasons, the latest `DECISION_HANDOFF`, the next smallest proof, and freeze readiness. Never give a fabricated “chance of winning.”
