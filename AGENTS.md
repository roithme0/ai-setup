# Kochwiki Agents Guide

## Mandatory Context Docs

- Before non-trivial work, read `docs/README.md`.
- Before running, building, testing, or setting up the environment, check root `README.md` for canonical commands.

## Coding Rules (Generic)

- No destructive commands.
- Prefer minimal changes and small diffs.
- Avoid wide refactors without explicit confirmation.
- Strict typing is required. Avoid `Any` and untyped parameters/returns.
- Keep code comments to a minimum; avoid commenting the obvious.

## Coding Rules (Backend)

- Do not use `from __future__ import annotations`; SQLModel/SQLAlchemy relationship typing can break with postponed annotation evaluation.

## Coding Rules (Frontend)

- Use Angular's `inject()` over constructor injection.
- Group public and private methods, wrapped in `//#region Public Methods` and `//#region Private Methods`.
- Prefer interfaces over types for object shapes in frontend code.
- Do not change `ChangeDetectionStrategy` without asking first.
- Before frontend UI/styling changes, read and follow `docs/frontend-style.md`.

## AI Workflow (Generic)

- For feature delivery sequencing and step gating, follow `AI Workflow (Spec-Driven Delivery)`.
- Ask before large refactors.
- If a user message is phrased as a question, answer it in chat first and ask for explicit confirmation before making code or file changes.
- Confirm before touching build or tooling config.
- Summarize changes and call out risks.
- Treat backend API as an internal contract for this repo's frontend by default: ship backend/frontend contract changes together, and do not preserve legacy compatibility unless explicitly required for a feature or an external consumer.
- Document important decisions in `docs/decisions.md` with a brief explanation (no need to ask first).
- Offer AI-setup improvements when impactful.

## AI Workflow (Spec-Driven Delivery)

For feature work, follow this sequence explicitly:

1. Sparring phase: Collaboratively develop the concept in chat until scope and behavior are clear.
2. Spec phase: Document the agreed sparring result in a spec file before implementation planning.
3. Spec review phase: Request explicit user review of the spec file and discuss details before suggesting a step-by-step implementation plan.
4. Plan phase: Propose a step-by-step implementation plan derived from the approved spec file.
5. Implementation phase: Execute exactly one planned step at a time, then pause for user review/discussion and wait for explicit go before starting the next step.
6. Final quality phase: After all planned steps are complete, re-check touched/impacted code and offer small, low-risk refactorings. Do not apply refactorings unless the user agrees.

Mandatory ordering constraints for the implementation plan:

- The first plan step must always run `docs-guidance-check` (when available) and address/handle findings according to policy.

## AI Workflow (Backend)

- None yet.

## AI Workflow (Frontend)

- Use the Angular MCP server to check frontend best practices/quality when practical; if not, explain why.

## Communication Preferences

- Keep responses concise.
- Be critical; Be a collaborator; point out potential issues and missed details.
- Ask clarifying questions when necessary.
- Clearly communicate uncertainties; minimize false statements.

## Project Skills

- Manual skills live in `skills/`.
- Backend scan: `skills/backend-quality-scan`.
- Frontend scan: `skills/frontend-quality-scan`.
- Docs guidance check: `skills/docs-guidance-check`.

## Secrets

- Never commit API keys or tokens.
- Use `.env` files for local secrets.
