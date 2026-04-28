# Frontend Style Audit Workflow

The purpose of this workflow is to derive a qualitative frontend style contract from images. The resulting style contract becomes the default AI-facing reference for future frontend work.

## Global Rules

- Base the audit on images first. Do not infer the style contract from code, framework defaults, or generic design preferences unless the user explicitly asks for that.
- If no suitable images are provided, ask the user for them before starting the audit.
- If the provided images do not cover an important area, request more images or explicit written answers before finalizing the style contract.
- Do not invent hidden states, motion behavior, or responsive behavior that are not visible in the provided evidence.
- Mark uncertain areas explicitly instead of filling gaps with assumptions.
- The resulting `docs/frontend-style.md` must describe visual behavior and usage patterns, not exact implementation values.
- Do not include exact pixel values, spacing values, font sizes, hex colors, or token values in the style contract.

## Required Inputs

The audit should not begin until at least one of these is available:

- screenshots of the current product
- screenshots of a desired reference product
- mockups or exported design images
- annotated image references supplied by the user

## Minimum Image Coverage

Request enough images to cover the main visual system. Prefer coverage across these areas when they exist:

- landing or home screen
- one content-heavy page
- one form, modal, or dialog state
- one navigation state
- one data-heavy or card/list-heavy screen
- mobile and desktop views if both matter for the project

If important parts of the product are missing from the image set, note the gap and request follow-up material.

## Workflow Phases

1. **Input check**
   Confirm whether the user wants to match an existing product, synthesize multiple references, or define a target style from inspiration images.

2. **Image request phase**
   If the user has not provided enough images, ask for them before continuing.
   Keep the request specific. Ask for the missing screen types or states rather than asking for "more screenshots" in general.

3. **Visual inventory phase**
   Review the images and list the recurring patterns that appear consistently:
   - page structures
   - spacing character
   - hierarchy patterns
   - surface treatment
   - component families
   - color usage roles
   - repeated visual motifs

4. **Evidence gap phase**
   Identify what cannot be confidently derived from the current images.
   Common gaps include:
   - responsive behavior
   - hover, focus, pressed, and selected states
   - motion and transitions
   - empty, loading, and error states
   - less common component variants

5. **Follow-up phase**
   Ask for either:
   - additional images that show the missing details, or
   - explicit written answers when the missing behavior cannot be shown easily through screenshots

   Keep clarification batches small. Ask only for the gaps that materially affect the style contract.

6. **Style synthesis phase**
   Convert the visible patterns into a qualitative style contract.
   The contract should describe:
   - the overall visual character
   - how layout and spacing behave
   - how emphasis is created
   - how colors are used by role
   - how surfaces, borders, and elevation behave
   - how common components should feel
   - what is fixed versus open to interpretation

7. **Contract drafting phase**
   Populate `docs/frontend-style.md` using `docs/templates/_template-frontend-style.md`.
   The contract should be concise, specific, and rule-oriented.
   Prefer statements like:
   - "Accent color is reserved for primary actions and active states."
   - "Layouts are compact and scan-friendly."
   - "Surfaces are softly separated rather than heavily elevated."

   Avoid vague summaries like:
   - "clean modern UI"
   - "nice professional look"

8. **Confidence check phase**
   Before finalizing, verify that every major section of the contract is supported by:
   - visible evidence from the images, or
   - explicit user clarification

   If a section remains under-supported, mark it as uncertain instead of hardening it into a rule.

## Output Requirements

The workflow output is a completed `docs/frontend-style.md` style contract.

That contract should:

- be written for future implementation work
- describe the look and feel in qualitative terms
- explain how visual emphasis, layout, and color usage work
- define what must remain consistent
- define where the assistant may adapt the design
- reference the images or sources it was derived from

That contract should not:

- include exact token values
- include exact measurements
- prescribe framework-specific implementation details unless the project already requires them
- claim behaviors that were not visible or explicitly confirmed
