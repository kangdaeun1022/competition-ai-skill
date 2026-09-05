---
name: self-refine-with-overfit-guard
description: Refine a competition submission from review feedback while preventing judge overfit, evidence drift, scope drift, demo regression, and uncontrolled complexity. Invoke for “수상최적화”, iterative refinement, feedback incorporation, or pre-submission optimization after a baseline and independent review exist.
metadata:
  short-description: 과적합 방지 수상 최적화
---

# Self-refine with an overfit guard

## Purpose

Improve the submission without optimizing to a single simulated judge, one loud critique, or a more elaborate story. The preferred change is the smallest reversible change that improves a rubric-relevant weakness while preserving verified facts, agreed scope, and a runnable demo.

Use this only after a baseline submission and an independent review exist. If they do not, create them first with `$review-competition-proposals` in adversarial mode or state that refinement is provisional.

## Freeze a baseline

Create `REFINEMENT_BASELINE` before changing anything:

```text
- artifact versions and hashes or immutable identifiers:
- OFFICIAL_NOTICE_LOCK and rubric version:
- PROBLEM_LOCK / DIFFERENTIATION_LOCK / excluded scope:
- claim-to-source register and implementation-truth labels:
- demo deterministic-path result and fallback status:
- scorecard by criterion and blind-pool finding IDs:
- complexity budget: time, people, permissions, build risk, rehearsal capacity:
```

Do not delete the baseline or overwrite its evidence. Every proposed revision gets an ID, intended criterion, source finding, expected benefit, cost against the complexity budget, owner, and rollback method.

## Select changes with anti-overfit gates

Evaluate a small batch of changes, then stop for review. A change is eligible only if it passes every applicable gate.

| Gate | Pass condition | Reject / defer when |
| --- | --- | --- |
| Rubric relevance | improves a named official criterion or removes a submission blocker | it only makes the artifact feel more impressive |
| Regression gate | no baseline-passing criterion, required file, factual claim, or acceptance test becomes worse | a gain hides a regression elsewhere or has not been compared with baseline |
| Complexity budget | cost fits remaining time, people, data/permission, build, and rehearsal capacity | it adds dependency, feature, or coordination beyond the locked budget |
| Evidence drift guard | affected claims still match primary sources, dates, assumptions, and evidence strength | wording becomes stronger, source context changes, or a plan becomes a result |
| Scope drift guard | problem, user, mechanism, and excluded scope still match the locked strategy | the change solves a different problem, adds a new persona, or expands the MVP |
| Demoability guard | the deterministic path, fallback, reset, and rehearsal still work with the change | success needs a live dependency, manual rescue, unprepared data, or an untested step |
| Single-judge overfit guard | at least two independent perspectives or the official rubric support the change | only one judge/pool preference supports it, especially when other evidence is neutral or negative |

Make exceptions only for an official-rule correction, a submission blocker, or a verified factual error. Record the exception and its new risk.

## Blind judge pools and holdout judges

Use **blind judge pools** for iteration: reviewers see the revised artifact and rubric but not the change author’s rationale, prior scores, or other reviewers’ comments. Never reuse the exact same feedback pool as the only acceptance signal.

Before revision, reserve separate **holdout judges** and their questions/cases. Use rotating blind validation judges for candidate batches. Keep the final holdout sealed until refinement stops; compare the best candidate with the baseline in randomized A/B order without labels, rationale or review history.

A holdout is consumed when its feedback is exposed. Record its ID and exposure date. Subsequent repairs require fresh unexposed questions and an isolated reviewer; replaying the consumed holdout is regression testing only. Review independence requires isolated contexts or human reviewers. A single-context roleplay is explicitly non-blind and cannot pass this gate.

Accept a candidate only when a predeclared criterion meaningfully improves in independent validation, no protected criterion regresses, and all factual/scope/demo gates pass. An unchanged score alone is insufficient reason to replace the simpler best version. Track evidence-backed improvements separately from subjective score fluctuations.

If a holdout judge materially disagrees, use an arbiter to inspect artifacts and rubric support. Do not rewrite toward the holdout’s personal preference; either preserve the baseline, make a narrower evidence-backed change, or collect the missing proof.

## Required rollback conditions

Immediately restore the latest passing baseline or remove the offending change when any condition occurs:

1. an official requirement, eligibility rule, submission format, or factual source is violated;
2. a regression gate detects a decline in a required criterion, implementation truth, or file-quality check;
3. evidence drift turns verified evidence into an unsupported, stale, broader, or causal claim;
4. scope drift changes the locked user/problem/intervention or consumes the protected complexity budget;
5. the demoability guard fails its deterministic path, fallback, reset, or rehearsal;
6. the change is supported only by a single judge and lacks official-rubric or independent corroboration;
7. a blind pool or holdout judge finds a new `must fix` issue whose severity exceeds the claimed gain.

Record `rollback condition → reverted revision IDs → preserved finding → next smallest test`. Rollback is a control, not a failure.

## Stop and freeze

Before starting, record a finite evaluation budget, meaningful-improvement threshold, patience and rehearsal reserve. Default to at most 40 evaluation opportunities and patience of 3 consecutive non-improving candidates, unless the user supplies a different bound. These are workflow defaults, not empirically optimal values. A request for 500 means at most 500 opportunities, never 500 mandatory revisions.

One opportunity is one independent reviewer assessment of one artifact version, including validation and holdout; eight judge assessments consume eight opportunities. Reserve enough for final holdout before spending on iteration. Record consumed opportunities even for rejected candidates; retries do not reset the count.

Stop when the budget/time reserve is reached, or patience is exhausted with no newly substantiated major defect. Stop a change line when improvement fails to reproduce in validation; retain the best version. Budget exhaustion with blockers yields NOT READY, never automatic freeze. Never increase the budget merely to obtain a pass.

Maintain an immutable original baseline and a separate best-passing-version pointer. Roll back only revision-owned changes or restore a separate candidate copy; preserve unrelated edits. Example: v8 gains differentiation but loses explanation or implementation feasibility → reject v8 and keep v7. Record the exact failed gate and evidence.

Stop iterating when the high-severity issue register is closed or consciously accepted with mitigation, the complexity budget is near its protected rehearsal reserve, and the holdout review passes. Freeze new functionality after this point; allow only compliance repairs, source corrections, or rehearsal-discovered blockers.

## Output

Return a change ledger, gate results, blind-pool and holdout outcomes, accepted/deferred/reverted changes, remaining budget, updated risk register, and a clear `FREEZE` or `NOT READY` decision with reasons. Never report a refined artifact as stronger merely because it contains more features or feedback rounds.
