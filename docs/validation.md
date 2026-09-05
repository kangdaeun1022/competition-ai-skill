# 9+2 migration validation

Scope: Core 9 entrypoints, Optional 2 entrypoints, internal protocols, aliases and refinement controls.

## Structural checks performed

- Ruby YAML parser: all 11 SKILL.md frontmatters parsed; name matches directory; supported name length/characters and description lengths passed.
- Every references/ Markdown link from skill entrypoints resolves to an existing file.
- No active $ invocation of the six retired independent skills remains under skills/.
- git diff --check passed.
- Six retired protocols retain their substantive content under analysis/planning/review/presentation references. Retired entrypoints are removed; prior versions remain recoverable in Git.
- Original Python quick_validate requires PyYAML, unavailable in the system Python. This pass uses Ruby YAML structural checks and manual contract inspection, not a claim of running that validator.

## Manual scenario walkthrough (not independent agent execution)

| Input / condition | Expected route or decision | Inspection result |
| --- | --- | --- |
| 수상작역설계 only | analysis → winner protocol, no full workflow | mapped in router and analysis |
| 문제채굴 / 차별화검증 | planning → corresponding protocol | mapped; no duplicate entrypoint |
| 질의응답 only | presentation → hostile Q&A only | explicit mode boundary |
| 악질심사 | review → eight perspectives, blind pools, arbiter | protocol linked and retained |
| Policy-only contest | operating plan/scenario, no forced product build | router/spec/demo agree |
| Single-context judging only | non-independent critique, holdout cannot pass | explicit limitation in review/refinement |
| v8 better differentiation, worse feasibility | reject v8, retain v7 | protected regression and best-version rollback |
| Holdout feedback already exposed | consumed; new independent holdout needed | exposure log and fresh-review rule |
| Request 500 evaluations | finite upper bound, count each reviewer assessment, stop early | explicit budget and patience rules |
| Budget exhausted with blockers | NOT READY | freeze cannot follow exhaustion automatically |
| Unrendered final file | submission QA unverified | freeze blocked pending inspection |

These are author walkthroughs of written behavior. Real automatic selection accuracy, isolated multi-agent execution and outcomes on actual competition materials have not been measured.

## Packaging and compatibility

README documents Core/Optional installation, Korean aliases and all six retired identifiers. Users with an installed older version must move those old folders outside the discovery path after backup. The repository change does not alter local skill installations.

The optional skills require neither a graph service nor external designer delivery. Artifact creation relies on available tools and requested formats; no upstream document-generation scripts are bundled.
