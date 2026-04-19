# Agents Guide

## Mandatory Context Docs

- Before non-trivial work, read `docs/README.md` and then load all task-relevant normative docs defined there.
- Before running, building, testing, or setting up the environment, check root `README.md` for canonical commands.

## Coding Rules (Generic)

- No destructive commands.
- Prefer minimal changes and small diffs.
- Avoid wide refactors without explicit confirmation.
- Strict typing is required. Avoid `Any` and untyped parameters/returns.
- Keep code comments to a minimum; avoid commenting the obvious.
- For user-facing German text, use proper umlauts (`ä`, `ö`, `ü`) and `ß`; do not replace them with transliterations like `ae`, `oe`, `ue`, or `ss`.

## Coding Rules (Backend)
- Do not use `from __future__ import annotations`; SQLModel/SQLAlchemy relationship typing can break with postponed annotation evaluation.

## Coding Rules (Frontend)

- Use Angular's `inject()` over constructor injection.
- Group public and private methods, wrapped in `//#region Public Methods` and `//#region Private Methods`.
- Prefer interfaces over types for object shapes in frontend code.
- Do not change `ChangeDetectionStrategy` without asking first.
- Before frontend UI/styling changes, read and follow `docs/frontend-style.md`.

## AI Workflow (Generic)

- For feature delivery sequencing and step gating, follow `docs/spec-driven-delivery.md`.
- Ask before large refactors.
- If a user message is phrased as a question, answer it in chat first and ask for explicit confirmation before making code or file changes.
- Confirm before touching build or tooling config.
- Summarize changes and call out risks.
- Treat backend API as an internal contract for this repo's frontend by default: ship backend/frontend contract changes together, and do not preserve legacy compatibility unless explicitly required for a feature or an external consumer.
- Document important decisions in `docs/decisions.md` with a brief explanation (no need to ask first).
- Offer AI-setup improvements when impactful.

## AI Workflow (Backend)

- None yet.

## AI Workflow (Frontend)

- Use the Angular MCP server to check frontend best practices/quality when practical.
- In this Codex sandbox, do not run frontend tests (`npm run test` / `ng test`) because process spawning is blocked (EPERM). Skip execution and clearly report that frontend tests were not run due to sandbox limitations.

## Communication Preferences

- Keep responses concise.
- Be critical; Be a collaborator; point out potential issues and missed details.
- Ask clarifying questions when necessary.
- Clearly communicate uncertainties; minimize false statements.

## Secrets

- Never commit API keys or tokens.
- Use `.env` files for local secrets.
