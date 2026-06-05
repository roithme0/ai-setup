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

## Core Features

List the features that define the project. Keep this section short and ordered by importance so contributors can quickly understand what matters most.

- **Primary feature**: `[Describe the single most important capability of the project, the user it serves, and the expected outcome.]`
- **Supporting features**:
  - `[Add the next most important feature if needed.]`
  - `[Remove this subsection if the project is centered around one core capability.]`

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

- Spec-Driven Delivery Workflow (`/.codex/workflows/spec-driven-delivery.md`)
- Frontend Style Audit Workflow (`/.codex/workflows/style-audit-workflow.md`)
