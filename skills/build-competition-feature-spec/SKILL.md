---
name: build-competition-feature-spec
description: Translate a validated competition product concept into a traceable service feature specification. Use for 기능명세서 or 공모전기능명세; policy-only entries need an operating plan unless product specifications are requested.
---

# Build the competition feature specification

Use the idea and evidence handoffs plus actual code/demo evidence. Resolve only consequential unknowns about MVP users, platforms and implementation status.

Define the shortest user journey proving the selected intervention. For each feature provide:
- feature ID, user role, problem/claim/criterion IDs and priority;
- preconditions, input and data provenance, action, output and postconditions;
- interface/screen and state transitions, loading/empty/error/permission/fallback states;
- business rules, validation, human decision authority and failure handling;
- dependencies, owner, effort assumption and acceptance test;
- implementation status (implemented/partial/mockup/plan) and artifact location.

Map feature→screen→data→rule→test→demo step; flag orphan features and unsupported claims. Protect agreed exclusions and complexity budget. Each proposed addition must replace an item or fit remaining verified capacity and improve a named criterion.

Return FEATURE_SPEC.md, MVP inclusions/exclusions, state-flow description, acceptance-test table, dependency/data gaps and implementation evidence. Use spreadsheet formats only when requested and available; do not require a fixed number of sheets. For a policy-only submission, give the accountable actors, decision rules, inputs, exception path and outcome measurement as an operating plan. Completion requires a testable path for the core claim and explicit status for every item.
