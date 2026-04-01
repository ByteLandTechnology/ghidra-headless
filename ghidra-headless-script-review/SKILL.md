---
name: "ghidra-headless-script-review"
description: "Phase skill for reusable headless Ghidra script authoring, review, registration, and contract-based audit."
phase: "script_authoring_review"
---

# Ghidra Headless Script Review

Use this phase skill when planning includes reusable headless Ghidra scripts,
script registration, or review expectations that must survive `speckit`
planning.

The canonical contract is [`./planning-brief.md`](./planning-brief.md). Use it
to shape planning outputs and to audit generated artifacts for missing or
weakened script-review requirements.

## Phase Focus

This phase covers:

- reusable headless Ghidra script authoring
- deterministic script inputs and outputs
- script registration and naming expectations
- review checklist obligations for generated plans

## Non-Negotiable Constraints

- Headless-only workflow. Script usage must stay compatible with headless
  analysis flows.
- Evidence-backed claims. Script behavior and review findings must point to
  observable output or tracked examples.
- Reproducible workflow expectations. Script invocation, parameters,
  registration, and review steps must be replayable.
- Reviewable Markdown outputs. Generated planning artifacts and findings remain
  inspectable as Markdown.
- No downstream `speckit` extension or constitution change is required.

## Required Inputs

- planned script purpose and target workflow stage
- expected script inputs, outputs, and deterministic behavior
- registration or naming expectations for reusable scripts
- required review checklist items and failure handling
- optional local overlays that only tighten the contract

## How To Use This Skill

1. Fill in [`./planning-brief.md`](./planning-brief.md) with the script scope,
   deterministic expectations, and review obligations.
2. Provide the brief to `speckit` as a file or inline paste.
3. Review the generated planning artifacts with the same contract.
4. If a required script rule is missing, refine or regenerate the artifacts
   rather than weakening the contract.

## Examples

- Audit-oriented example:
  [`./examples/script-authoring-review-audit.md`](./examples/script-authoring-review-audit.md)
- Contract violation example:
  [`./examples/contract-violation-example.md`](./examples/contract-violation-example.md)

## Next Step Routing

- Use this phase when the plan introduces new reusable scripts or changes to
  how scripts are reviewed and registered.
- Return to evidence when a missing detail is really about replay surfaces,
  artifact capture, or validation rather than script obligations.
- Return to this phase after `speckit` generates artifacts so the same
  checklist can catch weakened script-review requirements.
