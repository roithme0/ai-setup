# Frontend Style Guide (Draft v1)

This is a first-pass style baseline derived from the UI templates in `ui-tempaltes/`.
Keep this lightweight. Prefer small updates over large rewrites.
Use Angular Material as the primary component library; custom UI should extend Material rather than replace it.

## Visual Direction

- Mobile-first, utility app look.
- Calm, low-contrast base UI with one clear action accent.
- Dense content layout for data-heavy screens (lists, ingredients, steps).
- Friendly rounded geometry (cards, dialogs, chips, floating buttons).

## Reference Screens

- `ui-tempaltes/home-page.png`
- `ui-tempaltes/recipes-page.png`
- `ui-tempaltes/foodstuffs-page.png`
- `ui-tempaltes/foodstuff-detail-page.png`
- `ui-tempaltes/edit-foodstuff-dialog.png`
- `ui-tempaltes/user-select-page.png`

## Color Baseline

Canonical token names and values live in `frontend/src/style-tokens.scss`.

Rules:

- Use very light neutral background and surface tones.
- Keep high-contrast text on neutral surfaces for readability.
- Use accent color primarily for primary actions and active states.
- Use chart colors only for composition/status visuals.
- Keep backgrounds neutral and let accent color highlight actions.
- Do not introduce additional strong brand colors without discussion.
- Reserve chart colors for status/composition visuals (rings/donuts).

## Token Strategy

- `frontend/src/style-tokens.scss` is the single source of truth for reusable frontend color tokens.
- Map app semantic tokens to Angular Material system variables first (for example `--mat-sys-surface`, `--mat-sys-primary`).
- Add custom tokens only when Material has no fitting semantic role (for example chart segment colors).
- Prefer semantic names (`background`, `surface`, `text`, `accent`) over component-specific color names.
- Do not use abbreviations in token names; use full words (for example `small` instead of `sm`).

## Typography

- Use a clean sans-serif.
- Keep hierarchy shallow.
- Page title: strong, compact.
- Card/list primary text: regular to medium.
- Metadata (time, counts, helper text): muted color, smaller size.
- Prefer readable density over oversized spacing.

## Shape, Spacing, Elevation

- Radius: medium-to-large rounded corners on surfaces and controls.
- Shadows: soft, low elevation; avoid heavy depth effects.
- Spacing rhythm: compact vertical spacing in lists/forms, medium spacing between cards/sections.
- Keep touch targets comfortable for mobile.

## Component Patterns

- Top bar: left home/back icon, title, right-side secondary actions.
- Content cards: rounded, subtle border/shadow, neutral fill.
- Recipe overview cards: circular composition chart + title + duration.
- Tables/lists: dense rows with thin separators.
- List row leading marker: circular status/ring marker for each item.
- List row trailing action: inline edit icon where needed.
- Search + create: sticky bottom search field/chip plus floating add button.
- Detail view: stacked sections in rounded containers (ingredients, preparation, etc.).
- Dialog: rounded modal, compact form groups, clear primary save action at bottom.
- User selection: grid of simple avatar cards with label, plus floating add button.

## Forms and Inputs

- Compact inputs with clear labels.
- Keep units close to numeric values.
- Group related nutrition fields in one row when space allows.
- Primary submit action is accent-colored text/button, visually centered.

## Icons and Data Markers

- Use simple outlined icons with consistent stroke feel.
- Circular ring markers should stay visually consistent in size/stroke.
- Donut charts should use the same 3-segment color family across screens.

## Interaction and Motion

- Keep motion subtle and purposeful (open dialog, card/fab press states).
- Avoid decorative animation.
- Prioritize clarity and speed over visual effects.

## Guardrails (Do / Avoid)

- Do keep a neutral, soft background and rounded surfaces.
- Do use accent color primarily for actions.
- Do keep data screens compact and scannable.
- Avoid high-contrast neon palettes.
- Avoid sharp-cornered components mixed with rounded UI.
- Avoid large empty decorative sections on data-heavy pages.
