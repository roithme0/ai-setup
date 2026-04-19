# Docs Source-of-Truth Guide

This folder is intended to be mandatory project context for both humans and coding assistants.

## Project Goal

Ship a hobby cooking assistant built on a FastAPI backend and Angular frontend that leans into the AI ideas captured in `docs/ideas.md`, while using the project as a hands-on learning vehicle for core AI concepts such as context engineering, streaming, RAG, and related techniques.

## Repo Layout

- backend/
- frontend/

## Tech Stack

- Backend: Python + FastAPI + SQLModel/SQLAlchemy
- Frontend: Angular
- Database: PostgreSQL
- Migrations: Alembic
- Primary UI library: Angular Material

## Project Skills

- Manual skills live in `skills/`.
- Backend scan: `skills/backend-quality-scan`.
- Frontend scan: `skills/frontend-quality-scan`.
- Docs guidance check: `skills/docs-guidance-check`.
- Docs state sync (proposal-only): `skills/docs-state-sync`.
- Decisions prune pass: `skills/decisions-prune-pass`.

## Canonical Reading Order

1. `AGENTS.md` (repo root): global working rules and constraints.
2. `docs/README.md`: this contract and navigation.
3. `docs/decisions.md`: accepted architectural and workflow decisions.
4. `docs/spec-driven-delivery.md`: mandatory process for feature delivery sequencing and gates.
5. `docs/specs/*.md`: active feature specs and acceptance criteria.
6. `docs/frontend-style.md`: frontend UI style baseline for implementation consistency.
7. `docs/features.md`: current-state snapshot of currently available atomic user-facing capabilities (not a history log).
8. `docs/ideas.md`: backlog ideas (not commitments).

## Normative vs Informative

- Normative: `docs/README.md`, `docs/decisions.md`, `docs/spec-driven-delivery.md`, `docs/frontend-style.md`, `docs/features.md` and `docs/specs/*.md`.
- Informative only: `docs/ideas.md`.

If documents conflict, prefer:
1. Newer dated decision/spec content.
2. Then this reading order.

Reading order defines context-loading order; for direct conflicts, apply the precedence rules above.

## Operational Definitions

- Non-trivial change/work: any change that affects behavior, APIs, schemas, cross-layer integration (backend + frontend), or spans multiple files.
- Important project decision: a decision that changes architecture, data modeling, workflow policy, documentation governance, or external dependency strategy.

## Assistant Contract

- Treat normative docs as required context before making non-trivial changes.
- Required context means task-relevant normative docs; for `docs/specs/*.md`, read only specs related to the feature/area being changed.
- For feature work, treat `docs/spec-driven-delivery.md` as required context.
- For frontend UI/styling work, treat `docs/frontend-style.md` as required context.
- Cite the deciding file when implementing or reviewing behavior/API changes.
- Add important project decisions to `docs/decisions.md`.
- Keep new feature specs in `docs/specs/` and link them from relevant PR/notes.
- Create new specs from `docs/specs/_template-spec.md`.
- Keep spec-authoring rules centralized in `docs/specs/_template-spec.md` (do not duplicate/extend them in other docs).
