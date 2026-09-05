# Reverse-engineer winning entries

## Purpose

Turn public winner evidence into bounded strategy. This is not a personality profile of judges, a claim that public summaries represent every winning submission, or permission to imitate another team’s work.

## Required evidence layers

Use four visibly separate sections in this exact order. A conclusion may move to a later layer only when the prior layer supports it.

1. **Official judging criteria** — notice, rubric, FAQ, presentation rule, award category, and revision date. Quote the criterion faithfully; map it to the judge question and required proof.
2. **Public winning-entry patterns** — only information observable in official winner pages, demos, reports, press releases, or materials the user supplies. For each pattern record its source, sample size, year/category similarity, and counterexamples or coverage limits.
3. **Analysis hypotheses** — explain a possible connection between criterion and pattern, label confidence, and state what would falsify it. Do not call this an official rule.
4. **Our strategy** — choose an original response: the selected criterion, evidence to create, scope boundary, and reason it fits this team and contest. Keep it distinct from any other entrant’s expression or implementation.

Use the headings `공식 심사기준`, `공개 수상작 반복패턴`, `분석 가설`, and `우리 전략` in Korean outputs.

## Procedure

1. Lock the contest version: category, year, official sources, changes, and unknowns. If the user has not supplied them, research official sources before using secondary coverage.
2. Normalize the rubric into `criterion → score/priority → judge question → acceptable evidence → submission location`.
3. Collect public winner observations in a matrix. Separate a named winner’s facts from an interpretation. Do not claim to have read an unshared proposal.
4. Compare the observations only among materially comparable entries: same category, maturity, deliverable type, and year where possible. Note survivorship and publication bias.
5. Form no more than three hypotheses that affect a decision. Test each against contrary examples, the official rubric, and the team’s constraints.
6. Produce an original strategy card for each viable hypothesis. Reject it if it forces unsupported claims, copied expression, inaccessible data, or a larger MVP than the schedule can demonstrate.

## Output contract

Return:

| Layer | Finding | Source / observation scope | Confidence | Decision effect |
| --- | --- | --- | --- | --- |

Then include:

- rubric-to-proof map;
- winner-pattern matrix with observed and absent/unknown columns;
- hypotheses with disconfirming evidence to seek;
- `OUR_STRATEGY_LOCK`: problem, mechanism, proof, excluded scope, and collapse condition;
- a short `DECISION_HANDOFF` for problem mining.

## Guardrails

- “Repeated” means repeated within a stated public sample, not universal.
- Never turn an award title into proof of impact, technical validity, market demand, or judge preference.
- Do not use hidden scores, private submissions, personal data, or paid access the user has not authorized.
- Prefer an unglamorous but rubric-aligned proof over surface mimicry such as copying slide count, visual style, or buzzwords.
- When only one or two public examples exist, report observations, not patterns.
