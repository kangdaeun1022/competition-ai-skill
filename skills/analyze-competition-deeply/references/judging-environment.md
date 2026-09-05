# Analyze the judging environment

## Purpose

Model how the published evaluation is actually encountered by entrants and evaluators without inventing hidden preferences. This protocol complements the official rubric; it never overrides it.

## Questions

Investigate only with public or user-authorized evidence:

1. What stages exist: document screening, video, live demo, pitch, Q&A, mentor checkpoint, final panel?
2. What is the official or observed exposure time for each artifact?
3. How many tracks, categories and award paths exist, and what overlap restrictions apply?
4. Which sponsor APIs, datasets, policy goals or institutional missions are explicitly promoted?
5. What information is known about evaluator roles or published expertise? Do not infer private tastes or sensitive traits.
6. Are mentors, preliminary reviewers and final judges structurally connected according to public information?
7. Which artifact is likely to carry the most decision information: proposal, prototype, video, deck, demo or Q&A? Label inference separately from official fact.
8. What cognitive constraints are foreseeable: short review windows, many required criteria, remote viewing, projector/mobile readability, or demo network dependence?

## Strategic translation

Separate four layers:

- `OFFICIAL`: published rules and judging process.
- `OBSERVED`: public event format, prior schedules, winner materials and organizer statements.
- `HYPOTHESIS`: bounded inference about where evaluator attention or confusion risk may concentrate.
- `ACTION`: an ethical, rule-compliant response such as earlier proof, simpler visual, track selection, sponsor integration or stronger fallback.

Never recommend deception, fake live behavior, fabricated traction, undisclosed prerecorded output, copied winning work, manipulation of judges, or rule circumvention.

## Output

Return `JUDGING_ENVIRONMENT_MAP`:

| Stage | Exposure / constraint | Evidence layer | Decision question | Risk | Strategy |
| --- | --- | --- | --- | --- | --- |

Also return award-path map, sponsor/organizer fit signals, attention bottlenecks, unknowns and `strategy_invalid_if` conditions. Feed only evidence-backed actions into planning, demo and presentation.