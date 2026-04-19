# Spec-Driven Delivery Workflow

For feature work, follow this sequence explicitly:

1. Sparring phase: Collaboratively develop the concept in chat until scope and behavior are clear. Before requesting explicit user confirmation, ask all clarifying questions required to draft the spec; ask no more than 5 questions at a time. If more than 5 clarifications are needed, ask them in batches of 5 and only continue with the next batch after the previous answers are clarified. Treat this step as complete only after explicit user confirmation before moving to the spec phase.
2. Spec phase: Document the agreed sparring result in a spec file before implementation planning.
3. Spec review phase: Request explicit user review of the spec file and discuss details before suggesting a step-by-step implementation plan.
4. Plan phase: Propose a step-by-step implementation plan derived from the approved spec file.
5. Implementation phase: Execute exactly one planned step at a time, then pause for user review/discussion and wait for explicit go before starting the next step.
6. Final quality phase: After all planned steps are complete, re-check touched/impacted code and offer small, low-risk refactorings. Do not apply refactorings unless the user agrees.

Spec authoring guardrail:
- New specs must be created from `docs/specs/_template-spec.md`.
- Do not define separate spec-authoring process rules outside the template; keep them centralized in the template file.

Mandatory ordering constraints for the implementation plan:

- The first plan step must always run `docs-guidance-check` (when available) and address/handle findings according to `skills/docs-guidance-check/SKILL.md` (`Severity Rules`).
- The second-to-last plan step must run `decisions-prune-pass` to clean `docs/decisions.md`.
- The last plan step must always run `docs-state-sync` in proposal mode, using the pruned decisions state as input.
