# Frontend Style Contract Template

Use this template to create `docs/frontend-style.md` after completing the frontend style audit workflow.

This template is intentionally qualitative. It should describe the visual system in a way that helps humans and coding assistants preserve the intended look and feel during implementation.

## Authoring Rules

1. Base the contract on visual evidence from audit images and explicit user clarification.
2. Prefer concrete qualitative rules over broad adjectives.
3. Do not include exact pixel values, spacing values, font sizes, hex colors, or token values.
4. Do not claim interaction states, responsive behavior, or component variants that were not visible or explicitly confirmed.
5. Mark uncertain areas explicitly instead of hardening them into rules.
6. Keep the contract concise and implementation-oriented.
7. Treat this file as the default AI-facing style reference after it is created.

## Copy and Fill This File

```md
# Frontend Style Contract

Derived from: <screenshots | mockups | reference sites | mixed sources>
Date: YYYY-MM-DD
Status: draft | approved

## Purpose

<What this contract governs and where it should be applied.>

## Style Summary

<A short paragraph that describes the overall visual character of the UI in concrete qualitative terms.>

## Product Personality

- <Trait 1>
- <Trait 2>
- <Trait 3>

## Visual Principles

- <Durable rule about how the interface should feel or communicate>
- <Durable rule about emphasis, scanability, restraint, or tone>
- <Durable rule about consistency boundaries>

## Layout and Spacing Behavior

- <Compact vs spacious layout behavior>
- <How sections are separated>
- <How whitespace is used>
- <How dense or scan-friendly content areas should feel>
- <How layout should adapt at a high level across screen sizes, or "Unclear from audit">

## Color Usage

- <How accent color is used by role>
- <How neutral backgrounds and surfaces behave>
- <How emphasis is created without overusing strong color>
- <What kinds of color behavior should be avoided>

## Typography Behavior

- <Overall typographic tone>
- <How strong or restrained hierarchy should feel>
- <How headings, body text, and metadata differ in emphasis>
- <What should remain readable and understated>

## Shape and Surface Language

- <Rounded vs sharp geometry>
- <Flat vs layered presentation>
- <How borders, separators, and shadows are used>
- <How surfaces are distinguished from one another>

## Component Guidance

### Buttons and Actions

- <How primary, secondary, and low-emphasis actions should be presented>

### Forms and Inputs

- <How inputs, labels, and grouped controls should feel>

### Cards and Containers

- <How grouped content should be framed and separated>

### Navigation

- <How navigation should present hierarchy, orientation, and active state>

### Data Display

- <How lists, tables, metrics, or dense content should be presented>

### Overlays and Feedback

- <How dialogs, drawers, empty states, loading states, or error states should feel, or "Unclear from audit">

## Interaction and Motion

- <How restrained or expressive motion should be, or "Unclear from audit">
- <How interactive feedback should feel>
- <What kinds of motion or state changes should be avoided>

## Responsiveness

- <How the visual language should adapt across screen sizes, or "Unclear from audit">

## Do

- <Rule to preserve the intended style>
- <Rule to preserve emphasis or clarity>
- <Rule to preserve consistency>

## Avoid

- <Common drift pattern to avoid>
- <Color, spacing, or component misuse to avoid>
- <Visual tone that would break the intended style>

## Fixed vs Variable

### Fixed

- <Non-negotiable traits that should stay stable>
- <Patterns that future work should preserve>

### Variable

- <Areas where the assistant may adapt while staying on-style>
- <Areas where new components may interpret the style more freely>

## Evidence and Reference Anchors

- <Reference image or screen 1>
- <Reference image or screen 2>
- <Reference image or screen 3>

## Uncertainties

- <Behavior or area not fully supported by available evidence, or "None">

## Maintenance Rule

Use this file as the default style reference for frontend work until it is intentionally replaced by a new audit.
```
