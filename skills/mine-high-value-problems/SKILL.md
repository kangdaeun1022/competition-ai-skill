---
name: mine-high-value-problems
description: Discover, compare, and validate evidence-backed competition problems before solution ideation. Invoke for “문제채굴”, problem discovery, user pain points, public-policy bottlenecks, or high-value problem selection; do not use to invent solutions before the problem is evidenced.
metadata:
  short-description: 고가치 공모전 문제 채굴
---

# Mine high-value problems

## Purpose

Find a specific, consequential, and demonstrable problem that fits the official brief and the team’s ability to prove something within the competition horizon. A good problem is not merely large, fashionable, or easy to describe.

## Work from observable evidence

Build problem candidates from at least one of: official statistics or operational reports, a supplied field observation, a traceable user interview, a documented workflow, public complaint/usage data, or a reproducible data analysis. Separate:

- **fact** — what source says or what was directly observed;
- **interpretation** — a plausible meaning or root cause;
- **assumption** — something still to test;
- **opportunity** — the intervention boundary worth exploring.

If first-party user access is unavailable, do not fabricate interviews. Use an ethical no-contact validation ladder: public workflow evidence → publicly documented pain → proxy/user expert review → later validation plan.

## Candidate card

For every candidate, produce:

```text
PROBLEM_CARD
- affected user and concrete moment:
- current workflow / workaround:
- costly failure, delay, risk, or inequity:
- evidence and recency:
- root-cause hypothesis and alternative explanation:
- official-criterion link:
- team advantage / access constraint:
- smallest testable intervention:
- proof possible before deadline:
- excluded scope and collapse condition:
```

Avoid solution labels in the problem title. “AI matching app” is not a problem; “case workers cannot reliably identify which applicant needs follow-up before the response window expires” may be one, once evidenced.

## Rank without false precision

Score qualitatively or use a documented scale across:

| Dimension | Ask |
| --- | --- |
| Severity | What is lost when the current flow fails? |
| Frequency / reach | How often and for whom does it happen? |
| Evidence strength | Is the evidence direct, current, and relevant? |
| Rubric leverage | Which official criterion improves if this is proved? |
| Intervention leverage | Can a bounded change alter a decision or workflow? |
| Demoability | Can the cause→intervention→observable result path be shown? |
| Team fit | Do the team, data, time, and permissions make proof plausible? |

Do not sum arbitrary scores into an authoritative ranking. Explain the trade-off and retain a materially different backup candidate.

## Selection gate

Select a leading problem only when all statements are true:

- the affected person, moment, failure, and consequence are concrete;
- at least one decisive claim has a source or a named validation method;
- the proposed scope is smaller than the underlying social problem;
- a competitor, rule change, or missing permission would not make the entire proof impossible without a fallback;
- the leading problem improves an official criterion more than it increases complexity.

## Output

Return a problem landscape, candidate cards, the evidence gaps ordered by decision impact, leading and backup problems, rejected candidates with reasons, and a `PROBLEM_LOCK` that preserves the exact problem boundary for ideation and competitive-whitespace analysis.
