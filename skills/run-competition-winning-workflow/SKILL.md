---
name: run-competition-winning-workflow
description: Coordinate multiple stages of competition preparation from official source lock to submission freeze. Use for 공모전 or end-to-end preparation; route focused analysis, planning, evidence, specification, demo, presentation, review or refinement requests to their owner.
---

# Run the competition winning workflow

Use Core 9 skills by user intent. Read the selected installed skill before execution. If a sibling skill is not installed, read its repository SKILL.md when available; otherwise report the missing capability and continue only supported work. Do not claim an unavailable stage ran.

## Intent routing

| Intent / alias | Owner and mode |
| --- | --- |
| 공모전, 전체 진행 | this router |
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

## Official source lock and weighted routes

Begin with current official notice, corrections, FAQ, rubric and forms using analyze-competition-deeply. Lock source/version, requirements, eligibility, deadline/timezone, artifact constraints and unanswered questions. If a decisive official file is unavailable, state what cannot be locked.

Official weights always override these provisional planning priorities. These numbers are resource-prioritization defaults, not estimates of real judging or winning probability.

| Type | Provisional weights totaling 100 | Route adjustment |
| --- | --- | --- |
| Idea/policy | problem 30, public/policy fit 25, operations 25, communication 20 | operating plan and scenario proof; product spec only when applicable |
| AI/data | problem 20, data/AI/safety 30, evaluation/MVP 30, adoption 20 | data permission, non-AI baseline and evaluation before build |
| Hackathon | MVP/demo 35, value 25, difference 15, delivery 15, communication 10 | narrow core flow and protected rehearsal time |
| Capstone | technical depth 30, implementation 30, validation 20, impact/communication 20 | reproducibility, architecture and team contribution |

Set available time, people, permissions and rehearsal reserve as the complexity budget. Use the actual deliverable requirements for mixed competitions.

## Stage sequence and completion

1. Official source lock → analysis: criteria, organizer, winner reverse engineering and competitor patterns. Output CONTEST_ANALYSIS_HANDOFF.
2. Planning: problem mining, candidates, prior art/whitespace, AI fit and collapse conditions. Output IDEA_PLAN_HANDOFF with locked scope and explicitly untested assumptions.
3. Evidence deep research: classify every decisive claim and investigate contradictions. Output evidence register and claim matrix. Unresolved claims remain labeled and constrain the next stage.
4. MVP/features: product specification or policy operating plan with traceable acceptance criteria and implementation status.
5. Demo engineering: magic moment, deterministic path and recovery/rehearsal evidence; policy scenario when appropriate.
6. Presentation/Q&A: criterion-driven deck, script and answer cards within official time/format.
7. Independent review including adversarial pass: versioned findings and arbiter issue register.
8. Guarded refinement: candidate→regression gates→blind validation→accept/reject against best version. Return to review for changed artifacts within the finite evaluation budget.
9. After refinement stops, run reserved holdout once. If it fails, retain the passing best version or make authorized repairs with a fresh holdout; the consumed holdout is not reused as unseen evidence.
10. Refresh affected Q&A, complete submission QA and freeze the exact final artifacts.

Do not force optional skills or irrelevant artifact types. A requested partial stage can complete with explicit gaps; full submission freeze requires all relevant checks to pass.

## State and boundaries

Persist a compact WORKFLOW_STATE: official lock version, type/weights and provenance, problem/mechanism/exclusions, evidence and implementation status, artifact versions, issues, best version, evaluations consumed, budget remaining, next stage and reopen triggers.

All three review steps have different jobs: review finds defects, refinement controls changes, holdout checks the final candidate without iteration history. Delegate revisions only within user-authorized scope. Protect best-version snapshots and unrelated user edits.

Freeze prevents new scope after final QA. Reopen affected artifacts only for official corrections, verified factual defects or demonstrated blockers; rerun their checks. Freeze is preparation and does not itself authorize external submission.
