---
name: analyze-competition-deeply
description: Analyze competition notices, rubrics, organizer context, public winners, competitor patterns, judging stages and award paths. Use for 공모전분석 or 수상작역설계; idea-specific differentiation belongs to planning.
---

# Analyze a competition

Establish what this competition asks entrants to prove and how that proof reaches evaluators. Preserve official facts, observed patterns, analyst hypotheses and our strategy as separate evidence layers. Use stable IDs and shared contracts from `../../docs/contracts.md` when this skill participates in the full workflow.

1. Build OFFICIAL_NOTICE_LOCK from current official notice, amendments, FAQ, rubric and forms. Record URLs or supplied filenames, publication/effective/check dates, eligibility, deadline and timezone, required formats, allowed AI/data use, award categories and disqualification conditions. Missing decisive documents remain unresolved; do not invent rules.
2. Read [rubric-decoding](references/rubric-decoding.md) for every analysis. Translate each criterion into a judge question and observable proof.
3. Read [organizer-intent](references/organizer-intent.md) when institutional context affects topic selection.
4. For winner analysis or 수상작역설계, read [winner-reverse-engineering](references/winner-reverse-engineering.md). In full analysis run this when public examples are available; report unavailable coverage honestly.
5. Read [competitor-archetypes](references/competitor-archetypes.md) to identify the external competitive landscape. Leave comparisons with our specific mechanism to planning.
6. Read [judging-environment](references/judging-environment.md) for hackathons, live/demo stages, multi-track awards, sponsor-driven events, or whenever judging exposure and award paths materially affect strategy. Keep official process, observations and hypotheses separate.

Return CONTEST_ANALYSIS_HANDOFF: official lock/version, criterion ID→weight/priority→judge question→proof map, organizer facts/hypotheses, winner observations and limits, competitive archetypes, judging-environment map when applicable, award paths, unanswered official questions and affected decisions. Our strategy is provisional until problem selection; do not prematurely lock a solution from winner patterns. Reopen affected findings after an official correction.