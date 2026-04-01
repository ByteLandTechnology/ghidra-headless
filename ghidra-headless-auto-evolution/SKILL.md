---
name: "ghidra-headless-auto-evolution"
description: "Explicit child skill for extracting reusable improvements from real Ghidra work, resolving overlap, and promoting tracked assets when one task provides complete evidence."
phase: "auto_evolution"
---

# Ghidra Headless Auto Evolution

Use this child skill after a real task is complete and you need a reviewable
decision about whether an observed script, workflow step, documentation
pattern, or child-skill opportunity should become a supported tracked asset.

This skill does not replace intake, evidence, or script-authoring planning. It
mines already completed work for reusable value and records why the result
should be promoted, deferred, or rejected.

## Non-Negotiable Constraints

- Headless-only workflow. Auto evolution must not introduce GUI-only guidance.
- Evidence-backed decisions. Promotion claims must point to real reviewed
  artifacts.
- Markdown-first outputs. Review results remain inspectable as tracked
  repository documents.
- Runtime separation. Workspace-only helpers and generated outputs stay under
  `.work/`.
- Explicit invocation. The user or maintainer calls this skill intentionally;
  it is not a silent background behavior.

## Required Inputs

Every supported run must identify:

- the completed real task or artifact set under review
- the reviewed artifact paths, notes, scripts, or prior evidence records
- the parent skill or skill-family surface that may be updated
- the candidate summary describing what reusable behavior is under evaluation
- the sample-specific details that must not be generalized unchanged

## Invocation Pattern

Example request shape:

```md
Use `ghidra-headless-auto-evolution` for this follow-on review.

Source task scope:

- completed feature or analysis task with reviewable artifacts

Reviewed artifacts:

- repository-relative paths to the source corpus

Target skill scope:

- umbrella skill, existing child skill, or new child-skill entry

Requested outcome:

- promote_if_justified
```

## Output Set

Every supported run produces:

- a review record based on
  [`./templates/auto-evolution-review-record.md`](./templates/auto-evolution-review-record.md)
- one visible candidate classification outcome for each reviewed candidate:
  `accepted`, `deferred`, or `rejected`
- an embedded `Promotion Decision Log`
- an embedded `Asset Target Summary`
- direct asset paths for any created or updated tracked surfaces
- follow-up actions when a candidate is deferred or rejected

## Workflow

1. Confirm that the source material comes from a completed real task rather
   than brainstorming.
2. List the exact reviewed artifacts and the target skill surface that may
   change.
3. Extract one or more reusable candidates and record the sample-specific
   details that must stay local.
4. Check the four required proof elements:
   - task context
   - reusable-part summary
   - benefit statement
   - explicit non-sample-specific reasoning
5. Resolve overlap:
   - does the candidate extend an existing asset
   - duplicate one
   - or justify a new reusable path
6. Classify the candidate:
   - `accepted` when evidence is complete and overlap is resolved
   - `deferred` when value exists but proof or overlap handling is incomplete
   - `rejected` when the candidate is sample-specific, duplicative, or breaks
     repository boundaries
7. If the candidate is `accepted`, directly create or update the tracked asset
   only after naming the resulting repository paths.
8. Record follow-up actions and runtime-boundary notes for every non-promoted
   or partially promoted candidate.

## Decision Questions

Ask these questions for every candidate:

- What exact real task produced this candidate?
- Which part is reusable, and which part must remain sample-specific?
- What future workflow benefit does promotion create?
- Why is the candidate not just a one-off sample quirk?
- Which tracked asset should change, and why is that the right surface?
- Does the candidate extend an existing supported asset instead of requiring a
  new one?
- Are any related runtime helpers or generated outputs staying correctly under
  `.work/`?

## Direct Asset Creation Boundary

When the candidate is `accepted` and the evidence record is complete, this
skill may directly create or update:

- skill files
- templates
- workflow documents
- examples
- reusable scripts
- new child-skill entry points

Direct creation never implies automatic git commits, publishing, or approval
outside the repository workflow.

## Runtime And Overlap Rules

- Do not promote runtime-generated content directly from `.work/` into
  `.agents/skills/` without a separate reviewable justification.
- If a candidate depends on writing under `.agents/skills/` during live runs,
  reject or defer it until the runtime path is corrected.
- Prefer updating an existing tracked surface when the candidate cleanly
  extends it.
- Create a brand-new tracked path only after the overlap decision is explicit
  in the review record.

## Worked Examples

- Direct promotion:
  [`./examples/direct-promotion-example.md`](./examples/direct-promotion-example.md)
- Deferred or rejected path:
  [`./examples/deferred-candidate-example.md`](./examples/deferred-candidate-example.md)
- Public source corpus for this published skill:
  the two worked examples above, together with
  [`./templates/auto-evolution-review-record.md`](./templates/auto-evolution-review-record.md)
  and [`../ghidra-headless/SKILL.md`](../ghidra-headless/SKILL.md)

## Next Step Routing

- Return to the umbrella skill when the main question is which broader
  reverse-engineering contract to use next.
- Return to evidence when the gap is replay, extraction, or validation detail
  rather than reusable-improvement judgment.
- Return to script authoring and review when the candidate is clearly a new
  reusable script and now needs deterministic authoring and registration work.

## Cross-Links

- Umbrella routing:
  [`../ghidra-headless/SKILL.md`](../ghidra-headless/SKILL.md)
- Child-skill contract:
  [`./SKILL.md`](./SKILL.md)
- Reviewer flow:
  [`./templates/auto-evolution-review-record.md`](./templates/auto-evolution-review-record.md)
