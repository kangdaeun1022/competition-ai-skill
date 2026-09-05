# Shared workflow contracts

These contracts make handoffs machine-readable enough for downstream skills while keeping Markdown usable by humans. A skill may add fields but should not silently rename or drop required IDs.

## Stable IDs

Use stable prefixes: `R` rubric, `C` claim, `S` source, `P` problem, `D` differentiation, `F` feature, `M` demo step/magic moment, `A` artifact, `I` review issue, `V` version, `E` evaluation.

## WORKFLOW_STATE

```yaml
workflow_state:
  contest_id:
  official_lock:
    version:
    checked_at:
    sources: []
    unresolved: []
  contest_type:
  rubric_ids: []
  problem_lock:
  differentiation_lock:
  artifact_versions: []
  claim_status: []
  implementation_status: []
  issue_status: []
  best_passing_version:
  evaluation_budget:
    mode: light|standard|deep|custom
    consumed:
    reserved_holdout:
  next_stage:
  reopen_triggers: []
```

## CONTEST_ANALYSIS_HANDOFF

Required: official lock/version, rubric rows `criterion_id → official weight/priority → judge question → required proof`, organizer facts vs hypotheses, public winner observations with sample limits, competitor archetypes, judging-environment map when relevant, unanswered official questions and affected decisions.

## IDEA_PLAN_HANDOFF

Required: `PROBLEM_LOCK`, `DIFFERENTIATION_LOCK`, target user/moment, evidenced failure, causal mechanism, nearest alternative, residual difference, decisive assumptions, proof plan, collapse conditions, backup, MVP boundary, exclusions, owner/time/data constraints and unresolved claim IDs.

## EVIDENCE_REGISTER

Every decisive claim uses:

```yaml
claim:
  id: C001
  wording:
  type: observation|assumption|target|causal|result
  importance: decisive|supporting
  source_ids: []
  status: supported|partial|contradicted|unknown
  scope_conditions: []
  inferential_limits: []
  used_in_artifacts: []
  revalidate_if: []
```

Every source records source ID, title, publisher, URL/file, dates, exact location, methodology/scope, license/access, limitations and check date.

## REVIEW_HANDOFF

Each issue uses `issue_id`, artifact/version/location, rubric IDs, claim IDs, finding type (`confirmed_defect|unverified_concern|preference`), severity, blocker boolean, evidence, confidence, smallest remedy, regression risk and owner. Preserve disagreement rather than averaging it away.

## Contract rules

- Never promote `plan`, `mockup`, `fixture`, `simulation` or `prototype result` to implemented/live/impact without new evidence.
- A changed official source invalidates dependent rubric rows and downstream decisions.
- A changed claim invalidates all listed artifact usages until checked.
- Downstream skills consume IDs rather than paraphrased summaries when IDs exist.
- Human-readable output may be concise, but persisted handoffs must retain these fields.