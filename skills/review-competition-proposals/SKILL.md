---
name: review-competition-proposals
description: Audit competition submissions against official criteria, evidence, logic, implementation, communication reality and submission requirements. Use for 공모전검토 or 악질심사, the adversarial mode within this review.
---

# Review competition proposals

Review the supplied version independently. Establish official lock, artifact version, evidence register and implementation status. Use stable issue/claim/rubric IDs from `../../docs/contracts.md` when available. A review request produces findings; revision requires the user's requested edit scope.

1. Always read [official-rubric-review](references/official-rubric-review.md).
2. For claims and source verification read [evidence-attack](references/evidence-attack.md).
3. For a product, AI system or operational policy read [system-operation-attack](references/system-operation-attack.md).
4. For 악질심사 or a full independent pre-submission review read [adversarial-judge-pass](references/adversarial-judge-pass.md). Keep this within the same review issue register.
5. For decks, proposals, videos/scripts, demo narration or other evaluator-facing artifacts, read [communication-reality-audit](references/communication-reality-audit.md) during full review. Run the time-poor recall test and AI-slop audit without weakening evidence.
6. For final artifacts or freeze readiness read [submission-qa](references/submission-qa.md).

Return REVIEW_HANDOFF: reviewed version/rubric, criterion findings, blind-review conditions, issue IDs with severity/blocker status, artifact locations, sources, smallest remedies, disagreement/arbiter decisions, time-poor recall result when applicable and remaining uncertainties. Separate confirmed defects, unverified concerns and preferences. Unreadable or absent final artifacts cannot pass final submission QA.

Prioritize eligibility/submission blockers, factual and causal defects, implementation/operation failures, criterion-level persuasion failures, then cosmetic clarity. Route authorized iterative fixes to self-refine-with-overfit-guard. A score is a rubric-based diagnostic, never an award probability.