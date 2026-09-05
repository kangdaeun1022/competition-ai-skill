---
name: rank-competition-opportunities
description: Compare multiple competitions or tracks to decide where the team has the strongest award opportunity. Use for 대회추천, 공모전비교, 해커톤비교, 꿀통공모전, 참가우선순위 or when choosing among contests before full preparation.
---

# Rank competition opportunities

Choose where to spend scarce preparation time before optimizing a submission. This skill ranks opportunities; it does not claim a winning probability.

## Inputs

For every candidate competition or track, collect current official notice, eligibility, deadline, required artifacts, award structure, categories/tracks, judging criteria, sponsor requirements and known participation signals. Record the team's existing assets, skills, reusable project components, evidence, data access, available time and constraints.

## Score dimensions

Use a 0–5 evidence-backed scale for each dimension and record confidence and source basis.

- `rubric_fit`: alignment between team strengths/assets and official criteria.
- `asset_reuse`: how much verified code, data, research, domain knowledge or presentation material can be reused without forcing the idea.
- `execution_advantage`: ability to build and demonstrate the decisive proof within the deadline.
- `award_density`: number and breadth of relevant award paths relative to credible participation signals; never fabricate entrant counts.
- `track_accessibility`: whether a specific track/category reduces irrelevant competition or creates a natural team advantage.
- `organizer_fit`: fit with stated organizer/sponsor mission and required technology, separated from speculative preference.
- `evidence_readiness`: availability of strong problem, data and evaluation evidence.
- `demo_leverage`: ability to create a memorable, observable proof rather than a feature tour.
- `competition_intensity_risk`: strength of likely competing archetypes, open qualification barriers and maturity expectations.
- `submission_risk`: complexity, format, rights, eligibility, data or logistics risks that could invalidate the entry.

Official rubric and eligibility override all heuristic scoring. Missing participation data stays `unknown`; do not replace it with invented competition ratios.

## Ranking model

Produce both:

1. a transparent weighted score for prioritization, with weights derived from the user's goal and contest type; and
2. a qualitative `GO / CONDITIONAL / PASS` decision based on blockers and opportunity cost.

Do not convert the score into an award probability. A high score means stronger relative fit among the compared options, not likely victory.

When multiple award categories exist, score relevant tracks separately. Flag whether the rules allow or prohibit multi-track entry or overlapping awards; never assume prize stacking is permitted.

## Output

Return `OPPORTUNITY_RANKING_HANDOFF` with:

- candidate competition/track IDs and official source versions;
- eligibility and deadline blockers;
- dimension scores, confidence and evidence notes;
- relevant award paths and unknown participation signals;
- reusable assets and missing capabilities;
- top opportunity, backup opportunity and explicit reasons;
- `reconsider_if` triggers such as new FAQ, track closure, team change or conflicting deadline.

Route the selected opportunity to `$run-competition-winning-workflow` or `$analyze-competition-deeply` for source lock and full preparation.