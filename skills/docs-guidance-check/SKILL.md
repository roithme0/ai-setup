---
name: docs-guidance-check
description: Check pre-implementation documentation safety by validating consistency and semantic guidance quality between `AGENTS.md` and core documentation governance files (especially `docs/README.md`). Use when the user asks for a documentation guidance scan, asks whether instructions/guidelines conflict or make sense, or before larger implementation changes. This skill reports findings and proposed fixes only; it does not apply changes unless explicitly asked.
---

# Docs Guidance Check

## Overview

Run a focused consistency scan across project instructions and documentation governance files used as pre-implementation guardrails. Detect contradictions, stale references, missing required files, and invalid canonical paths.

Default behavior is report-only.

## Scope

Check these files first:

- `AGENTS.md`
- `docs/README.md`
- `docs/decisions.md`
- `docs/specs/*.md` (existence and references only, unless user asks for deep content checks)

## Workflow

1. Read authoritative context
- Read `AGENTS.md` and `docs/README.md`.
- Parse normative/informative doc classification from `docs/README.md`.

2. Validate structural consistency
- Confirm all docs listed as normative exist.
- Confirm removed files are not still referenced as required.
- Confirm canonical paths used in instructions actually exist (for example `docs/specs/*.md`).

3. Validate instruction compatibility
- Check whether `AGENTS.md` guidance conflicts with `docs/README.md` precedence/contract.
- Flag broad instructions that force unnecessary full-folder scans when a scoped rule exists.
- Check whether workflow guardrails in `docs/decisions.md` contradict `AGENTS.md` or `docs/README.md`.
- Check whether references to the `docs/features.md` format are aligned across docs/skills.
- Check whether docs/skills consistently treat `docs/features.md` as a current-state availability list (not a history log).

4. Validate semantic sanity (mandatory)
- Check whether instructions in `AGENTS.md` and `docs/README.md` are actionable and testable (not vague).
- Check whether wording is clear enough that two assistants would likely take the same action.
- Check for undefined, overloaded, or circular terms that can cause interpretation drift.
- Check for practical conflicts where guidance is technically compatible but unrealistic or likely to fail in real workflows.
- Propose concrete wording changes when issues are found.

5. Return a concise report
- Group findings by severity: `High`, `Medium`, `Low`.
- Include file evidence for every finding.
- Include a short "Proposed Fixes" section.
- Do not edit files unless the user explicitly requests implementation.

## Explicit Non-Goals

- Do not propose sync updates between `docs/decisions.md`, `docs/features.md`, and `docs/ideas.md`.
- Do not evaluate feature/idea drift signals.
- Delegate drift/sync analysis to `docs-state-sync`.

## Severity Rules

- High: contradictory rules, missing normative files, or guidance that can mislead implementation.
- Medium: stale or ambiguous guidance that may cause drift.
- Low: wording/clarity improvements without functional risk.

## Output Template

Use this format:

Consistency Scan Result:
- Scope:
- Checked files:
- Overall status: `pass | issues-found`

High:
- [id] Finding
  - Evidence:
  - Impact:
  - Proposed fix:

Medium:
- [id] Finding
  - Evidence:
  - Impact:
  - Proposed fix:

Low:
- [id] Finding
  - Evidence:
  - Impact:
  - Proposed fix:

Open Questions (only if blocking):
- ...
