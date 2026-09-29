# Dashboard UI Guidelines

These rules distill useful product-interface patterns from Supabase Studio without copying its implementation.

## 1. Treat the application shell as one system
Design header, sidebar, secondary panels, content width, mobile navigation, and focus behavior together. A dashboard should not be a collection of unrelated page layouts.

## 2. Prefer semantic visual roles
Use named roles such as surface, raised control, muted text, border, selected state, and destructive state. Map those roles to the destination design system instead of scattering literal colors throughout components.

## 3. Build reusable data primitives
Common patterns should have stable structures:
- stat: label + value + optional icon/action
- status: state + accessible text
- empty table: explicit no-results message and relevant filter/search context
- sort/filter: visible control with clear current state
- dense table: stable columns, row identity, overflow strategy, and responsive behavior

## 4. Empty is a real state
For tables and lists, distinguish at least:
- no data exists
- current filter/search returned no results
- data is loading
- data is unavailable/error

Do not use a blank table area to represent all of these states.

## 5. Tooltips add context; they do not replace semantics
Use tooltips for explanations, shortcuts, or extra context. Keep accessible names and visible labels where the control needs them. Tooltip wrappers must preserve the underlying control's focus and interaction behavior.

## 6. Dense data needs a rendering strategy
For small datasets, normal rendering is preferable. For genuinely large datasets, consider virtualization. When virtualizing, preserve stable row keys, sticky headers where useful, empty states, scrolling behavior, and keyboard/focus semantics.

## 7. Responsive dashboard shells are not desktop-only
Provide a deliberate mobile navigation pattern. Check sidebar collapse/overlay behavior, content width, horizontal overflow, tables, fixed elements, and focus restoration after opening/closing navigation.

## 8. Accessibility belongs in the base layout
Include skip navigation where appropriate, a meaningful main landmark, keyboard-reachable controls, visible focus, and correct semantics. Do not wait until page-level QA to discover that the application shell blocks keyboard users.

## 9. Apply this with the existing standards
Combine these rules with:
- guidelines/ui-quality.md
- guidelines/operational-data-ui.md
- guidelines/responsive.md
- guidelines/css-isolation.md
- guidelines/design-system-evidence.md

Supabase is a reference source, not a requirement to reproduce its visual language.