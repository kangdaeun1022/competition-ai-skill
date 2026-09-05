# Architect a judge-first deck

## Purpose

Build a presentation that helps a judge answer the official evaluation questions with less inference. A visually polished deck that does not resolve a criterion is secondary to a clear, evidenced argument.

## Build from questions, not chapters

First translate the official rubric and likely objections into a finite question list. For every required slide, use this invariant:

```text
judge question → slide → evidence → visual → takeaway
```

The slide is unnecessary unless it answers a real criterion question, resolves a consequential objection, or enables the magic-moment demo. Do not use generic market, technology, or team slides merely because a standard pitch deck contains them.

## Slide contract

Create a planning table before drafting:

| Judge question | Official criterion / source | Slide title as answer | Evidence and status | Visual proof | One takeaway | Speaker proof / transition |
| --- | --- | --- | --- | --- | --- | --- |

Rules for each field:

- **Judge question:** word it as a skeptical decision question, not a topic label.
- **Slide:** make the title a defensible answer. State uncertainty when needed.
- **Evidence:** link to a primary source, validation method, prototype output, or clearly labeled plan. Preserve implementation truth.
- **Visual:** choose the smallest visual that reduces cognitive work—workflow, comparison, screenshot, chart, decision path, or one table. Charts require units, source, timeframe, and the decision implication.
- **Takeaway:** one memorable conclusion that stays within the evidence.
- **Speaker proof:** state what the presenter will say, show, or defer in Q&A; provide an explicit bridge to the next question.

## Recommended question sequence

Use only the questions relevant to the rubric:

1. Why is this precise problem important now, for whom, and under what evidence?
2. Why does the current approach fail at the identified decision point?
3. What is the bounded intervention, and why is it better than the nearest alternative?
4. Why is the mechanism feasible, safe, and appropriate—including non-AI alternatives where applicable?
5. What is implemented or otherwise demonstrable today?
6. How does the demo prove the magic moment?
7. What outcome will be measured, against what baseline, with what limitations?
8. How can this be operated, governed, sustained, and expanded without exceeding scope?
9. Why is this team credible to execute the next smallest step?

For a policy/idea contest, replace implementation details with a believable operating pathway and accountable owner. For AI/data, include data provenance, model necessity, evaluation, error path, and human authority. For a hackathon, bring the magic moment forward. For a capstone, make architecture and implementation evidence explicit.

## Stress test

Remove, merge, or defer a slide when it adds no new evidence or causes an unanswerable claim. Check that a judge can trace every decisive assertion to an artifact, source, or validation plan, and that the deck’s labels agree with the demo. Run `$review-competition-proposals` in adversarial mode on the resulting deck before late-stage polish.

## Output

Return the judge-question map, slide contract table, slide order and time budget, visual/evidence inventory, speaker notes, claim-risk list, and a version-ready deck outline. Mark all `[기준 설정 필요]` metrics and incomplete artifacts rather than filling them with invented numbers.
