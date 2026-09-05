# Simulate adversarial judges

## Purpose

Find reasons a serious evaluator could reject, downgrade, distrust, or fail to understand the submission before a real panel does. Simulate disciplined perspectives, not invented people, hidden scoring systems, or personal biases.

## Inputs and blinding

Use the official notice/rubric, current deck, proposal, demo path, evidence register, implementation-truth labels, and constraints. If the information exists, remove team names, affiliations, prior feedback, and order-of-preference signals from the review packet. Mark every missing artifact.

Run reviewers independently: each reviewer sees the same rubric and review packet but **never another simulated reviewer’s notes** before submitting a verdict. Do not give a reviewer the desired conclusion or proposed changes.

Use isolated agent contexts or separate human reviewers for independent passes, with only the rubric, common packet and assigned lens supplied. Run in batches when concurrency is limited. Record reviewer/session IDs, packet version and what each reviewer received; keep notes separate until the arbiter stage. These are simulated perspectives, not real contest judges.

If isolated contexts are unavailable, provide a labeled single-context multi-perspective critique. Do not claim blindness or independence and do not use it as a passing independent/holdout gate. Preserve team capability evidence when redacting names so reviewers can still assess execution.

## Required independent perspectives

Use every perspective below. Add a domain-specific reviewer only when it changes an official criterion or material risk.

| ID | Independent judge perspective | Primary attack |
| --- | --- | --- |
| J1 | Eligibility and rubric auditor | rule violations, missing deliverables, weak criterion-to-evidence links |
| J2 | Problem and stakeholder skeptic | unproven pain, wrong user, alternative root causes, adoption friction |
| J3 | Evidence and causal-inference auditor | stale or weak sources, unsupported numbers, causation claims, invalid comparison |
| J4 | Technical / data / safety reviewer | feasibility, data rights, AI necessity, reliability, privacy, failure handling |
| J5 | Differentiation and prior-art reviewer | existing substitutes, superficial novelty, untested competitive claim, rights signal |
| J6 | Execution and operations reviewer | owners, timeline, cost, governance, maintenance, dependency and scale risks |
| J7 | Demo and communication reviewer | unclear value, non-deterministic demo, implementation overclaim, visual or narrative gap |
| J8 | Impact and measurement reviewer | outcome logic, baselines, unintended harms, measurement and evaluation plan |

## Blind pools and arbiter

Create two blind judge pools with independent working notes:

- **Pool A: viability and truth** — J1, J3, J4, J6.
- **Pool B: value and persuasion** — J2, J5, J7, J8.

The pools may receive redacted descriptions of the same artifacts but cannot see the other pool’s scores, identities, or recommendations. Each perspective returns `criterion affected → finding → artifact location → evidence → severity → smallest remedy → confidence`.

After both pools finish, appoint an **arbiter**. The arbiter does not average opinions mechanically and does not invent a new personal taste. It:

1. checks each finding against the official rubric and supplied artifacts;
2. groups duplicate findings but preserves meaningful disagreement;
3. resolves conflict by preferring evidence and criterion relevance over rhetorical force;
4. labels a remedy `must fix`, `high leverage`, `optional`, or `not supported`;
5. identifies questions that must remain for a holdout review rather than being optimized away.

## Review discipline

- Attack claims and artifacts, not the team.
- A severe finding needs a cited artifact location or a clearly stated missing artifact; do not turn vague skepticism into a blocker.
- Distinguish an actual defect from an unverified concern and a personal preference.
- Offer the smallest remedy that changes the evaluation, not an automatic rewrite or feature expansion.
- Score only against an official rubric or a declared provisional rubric; do not manufacture award probabilities.

## Output

Return the two blind pool reports, the arbiter’s prioritized issue register, a criterion traceability matrix, disagreement log, unresolved holdout questions, and a baseline scorecard for `$self-refine-with-overfit-guard`.
