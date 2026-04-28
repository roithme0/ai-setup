---
name: frontend-quality-scan
description: Scan the `frontend/` codebase for architectural and readability issues in Angular code. Use when the user asks to scan or check frontend code quality, identify top issues, or request a short list of refactoring targets in the frontend.
---

# Frontend Quality Scan

## Overview

Provide a quick, high-signal scan of the frontend for the most important *architectural* and *readability* issues, limited to a maximum of three items. This skill must **not** make changes; it only reports room for improvement.

## Workflow

1. **Check repo instructions**
   - Look for `AGENTS.md` or other project rules and follow them.
   - Respect: no destructive commands. This skill never edits files.
   - Use the Angular MCP best-practices tool when practical; if not, explain why.

2. **Scan scope**
   - Only scan `frontend/` unless the user explicitly broadens scope.
   - Prefer `rg` to locate hotspots or patterns (e.g., very long components, repeated UI logic, deep template nesting, unclear naming).
   - Avoid syntax/style linting; focus on higher-level concerns.

3. **Prioritize findings**
   - Focus on architecture, readability, UI logic risks, and maintainability.
   - Prioritize unclear boundaries, overly complex flow, misleading naming, and oversized components.
   - Prefer issues with clear evidence and a plausible improvement direction.
   - Avoid speculative or purely stylistic nits.

4. **Respond with max 3 items**
   - If fewer than three issues are found, return only the issues found.
   - Add an implementation effort estimate to each suggestion using:
     - `low`: small localized change, little/no contract impact.
     - `medium`: touches multiple files/modules or needs careful regression checks.
     - `high`: cross-layer/architectural change, migration, or significant testing/coordination.
   - Each item must include:
     - **Issue** (short name)
     - **Impact** (why it matters)
     - **Evidence** (file path and brief cue)
     - **Suggestion** (high-level improvement direction; no code changes)
     - **Effort** (`low` | `medium` | `high`, implementation effort)

## Output Template

Use this format, with a clear divider between issues:

- - -
- Issue:
- Impact:
- Evidence:
- Suggestion:
- Effort:
