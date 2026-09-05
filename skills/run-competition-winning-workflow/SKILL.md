---
name: run-competition-winning-workflow
description: Coordinate competition preparation from opportunity selection or official source lock to submission freeze. Use for 공모전 or end-to-end preparation; route focused comparison, analysis, planning, evidence, specification, demo, presentation, review or refinement requests to their owner.
---

# Run the competition winning workflow

Use the installed competition skills by user intent. Read the selected skill before execution. Persist stable IDs and handoffs using `../../docs/contracts.md`. If a sibling skill is not installed, read its repository SKILL.md when available; otherwise report the missing capability and continue only supported work. Do not claim an unavailable stage ran.

## Intent routing

| Intent / alias | Owner and mode |
| --- | --- |
| 공모전, 전체 진행 | this router |
| 대회추천, 공모전비교, 해커톤비교, 꿀통공모전, 참가우선순위 | rank-competition-opportunities |
| 공모전분석, 수상작역설계 | analyze-competition-deeply; winner protocol for the latter |
| 공모전기획, 문제채굴, 차별화검증 | plan-competition-ideas; requested internal protocol |
| 공모전딥리서치, 근거자료집 | build-competition-evidence-pack |
| 기능명세서, 공모전기능명세 | build-competition-feature-spec |
| 데모설계 | engineer-competition-demo |
| IR덱, 발표설계, 질의응답 | prepare-competition-presentation; Q&A-only when requested |
| 공모전검토, 악질심사 | review-competition-proposals; adversarial mode for the latter |
| 수상최적화, 반복개선 | self-refine-with-overfit-guard |
| 자료관계분석 (optional) | map-competition-materials |
| 디자인제안서 (optional, designer handoff requested) | prepare-design-brief |

Focused aliases select a mode, not the whole process. Full-process work resumes from valid handoffs and reruns only stages invalidated by changed rules, evidence or scope.

## Source lock and contest-specific routes

When the contest is not yet chosen, rank opportunities first. Once chosen, begin with current official notice, corrections, FAQ, rubric and forms using analyze-competition-deeply. Lock source/version, requirements, eligibility, deadline/timezone, award paths, artifact constraints and unanswered questions.

Official weights always override provisional priorities. Planning weights are resource-allocation heuristics, never award probabilities.

- Idea/policy: problem, public/policy fit, operating mechanism and communication dominate; do not force product features.
- AI/data: establish data permission, non-AI baseline, evaluation design and failure/human-authority path before feature expansion.
- Hackathon: use a **magic-moment-first branch**. After problem and criterion lock, define the observable judge promise and demo storyboard before expanding the feature specification. Build only the shortest implemented path needed to prove it, then harden fallback/reset/rehearsal.
- Capstone: preserve technical depth, reproducibility, architecture, implementation evidence, validation and team contribution even when the demo is simplified.

Set available time, people, permissions and rehearsal reserve as the complexity budget.

## Stage sequence

1. Optional opportunity ranking when multiple contests/tracks are in play.
2. Official source lock → analysis: rubric, organizer, winner patterns, competitor archetypes, judging environment and award paths when relevant. Output CONTEST_ANALYSIS_HANDOFF.
3. Planning: problem, candidates, prior art/whitespace, AI fit and collapse conditions. Output IDEA_PLAN_HANDOFF.
4. Evidence research: classify every decisive claim, seek contradictions and produce the EVIDENCE_REGISTER.
5. Build path by contest type:
   - hackathon: magic moment/demo storyboard → minimal feature path → deterministic demo hardening;
   - product/capstone: MVP feature spec → demo engineering;
   - policy/idea: operating scenario and accountable decision path.
6. Presentation/Q&A: criterion-driven deck, script and answer cards. Bring the magic moment forward for hackathons.
7. Independent review including adversarial and communication-reality audits: versioned findings and arbiter issue register.
8. Guarded refinement: candidate → regression gates → blind validation → accept/reject against best version within finite evaluation budget.
9. After refinement stops, run reserved holdout once. Exposed holdouts are consumed.
10. Refresh affected Q&A, complete submission QA and freeze exact final artifacts.

## State and boundaries

Persist WORKFLOW_STATE using the shared contract: official lock, contest type/rubric provenance, problem/mechanism/exclusions, evidence and implementation truth, artifact versions, issue IDs, best passing version, evaluation budget, next stage and reopen triggers.

Review finds defects; refinement controls changes; holdout checks the final candidate without iteration history. Protect best-version snapshots and unrelated user edits. Freeze prevents new scope after final QA and does not authorize external submission.