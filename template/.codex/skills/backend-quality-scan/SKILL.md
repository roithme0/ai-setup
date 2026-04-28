---
name: backend-quality-scan
description: Scan the `backend/` codebase for code quality issues and refactoring opportunities. Use when the user asks to scan or check backend code quality, identify top issues, or request a short list of refactoring targets in the backend Python/FastAPI code.
---

# Backend Quality Scan

## Overview

Provide a quick, high-signal scan of the backend for the most important *architectural* and *readability* issues, limited to a maximum of three items. This skill must **not** make changes; it only reports room for improvement.

## Workflow

1. **Check repo instructions**
   - Look for `AGENTS.md` or other project rules and follow them.
   - Respect: no destructive commands. This skill never edits files.

2. **Scan scope**
   - Only scan `backend/` unless the user explicitly broadens scope.
   - Prefer `rg` to locate hotspots or patterns (e.g., very long functions, repeated logic blocks, deep nesting, large classes, unclear naming).
   - Avoid syntax/style linting; focus on higher-level concerns.

3. **Run tests and evaluate**
   - Run backend tests from `backend/`: `.\.venv\Scripts\python.exe -m pytest -q`
   - Summarize failures (if any) and consider them in the findings.
   - If tests cannot be run, state why and what would be needed.

4. **Prioritize findings**
   - Focus on architecture, readability, logic risks, and maintainability.
   - Prioritize unclear boundaries, overly complex flow, misleading naming, and oversized functions.
   - Prefer issues with clear evidence and a plausible improvement direction.
   - Avoid speculative or purely stylistic nits.

5. **Respond with max 3 items**
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

Test Results:
- Status:
- Summary:
- If not run:

- - -
- Issue:
- Impact:
- Evidence:
- Suggestion:
- Effort:
