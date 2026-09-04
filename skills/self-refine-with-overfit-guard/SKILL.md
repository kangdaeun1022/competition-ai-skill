---
name: self-refine-with-overfit-guard
description: Refine a competition submission from review feedback while preventing judge overfit, evidence drift, scope drift, demo regression, and uncontrolled complexity. Invoke for “수상최적화”, iterative refinement, feedback incorporation, or pre-submission optimization after a baseline and independent review exist.
metadata:
  short-description: 과적합 방지 수상 최적화
---

# Self-refine with an overfit guard

## Purpose

Improve the submission without optimizing to a single simulated judge, one loud critique, or a more elaborate story. The preferred change is the smallest reversible change that improves a rubric-relevant weakness while preserving verified facts, agreed scope, and a runnable demo.

Use this only after a baseline submission and an independent review exist. If they do not, create them first with `$simulate-adversarial-judges` or state that refinement is provisional.

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

Reserve one or more **holdout judges**—independent rubric perspectives that do not see iteration notes or proposed remedies—until a candidate revision batch is complete. The holdout packet should be blinded to baseline/revision labels where feasible and ask the same criterion questions. A change is accepted only when the holdout result confirms that the material criterion improved or did not regress.

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

Stop iterating when the high-severity issue register is closed or consciously accepted with mitigation, the complexity budget is near its protected rehearsal reserve, and the holdout review passes. Freeze new functionality after this point; allow only compliance repairs, source corrections, or rehearsal-discovered blockers.

## Output

Return a change ledger, gate results, blind-pool and holdout outcomes, accepted/deferred/reverted changes, remaining budget, updated risk register, and a clear `FREEZE` or `NOT READY` decision with reasons. Never report a refined artifact as stronger merely because it contains more features or feedback rounds.
