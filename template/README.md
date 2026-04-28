# Project Context Guide

This file is intended to be mandatory project context for both humans and coding assistants.

Use it as the root documentation contract for your project. Replace the placeholder content below with project-specific details, and remove sections or lines you will not maintain.

## Project Snapshot

- **Project name**: `[Replace with your project name]`
- **Project goal**: `[Describe what the project is for, who it serves, and the main outcome it should deliver.]`
- **Main repository areas**:
  - `[Example: backend/]`
  - `[Example: frontend/]`
  - `[Add or remove entries to match your repo.]`

## Tech Stack

- **Backend**: `[Replace or remove]`
- **Frontend**: `[Replace or remove]`
- **Database**: `[Replace or remove]`
- **Migrations**: `[Replace or remove]`
- **Primary UI library**: `[Replace or remove]`
- **Other important tooling**: `[Add items worth knowing before implementation]`

## Canonical Reading Order

1. `AGENTS.md` (repo root): global working rules and constraints.
2. `README.md`: this contract and navigation.
3. `docs/specs/*`: active feature specs and acceptance criteria. Remove if unused.
4. `docs/frontend-style.md`: frontend UI style baseline for implementation consistency. `[Remove if the project does not contain a UI.]`

## Workflows

Use workflows only when explicitly prompted to do so by the user.

- Spec-Driven Delivery Workflow (`/docs/workflows/spec-driven-delivery.md`)
- Frontend Style Audit Workflow (`/docs/workflows/style-audit-workflow.md`)

## Assistant Contract

- For frontend UI or styling work, treat `docs/frontend-style.md` as required context if your project uses it. `[Remove if the project does not contain a UI.]`
- Keep new feature specs in `docs/specs/` and create them from `docs/templates/_template-spec.md` if your project uses spec-driven delivery.
- Keep spec-authoring rules centralized in `docs/templates/_template-spec.md`; do not duplicate or extend them in other docs.
