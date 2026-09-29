# Supabase UI Reference

Source: https://github.com/supabase/supabase

Supabase is used here as a reference for production-grade product/dashboard UI, not as code to copy wholesale. The most relevant material is the shared UI package and Studio dashboard components.

## What is useful

### 1. Shared component library as a contract
Supabase maintains a shared React UI package built around Radix UI primitives and shadcn/ui. Its README explicitly treats the package as a common component library and recommends semantic surface/color roles rather than scattered hardcoded colors.

For this repository, extract the principle rather than the React/Tailwind implementation:
- prefer reusable components over one-off markup
- define semantic roles for surfaces, text, borders, controls, and muted content
- keep visual tokens consistent across a product
- do not turn an implementation-specific class name into a universal rule without evidence

### 2. Dashboard layout is a product system
Studio's DefaultLayout demonstrates a persistent application shell with:
- top/header area
- first-level sidebar navigation
- mobile navigation variant
- resizable secondary/sidebar content
- a dedicated main content region
- skip-to-content accessibility support
- explicit viewport-height handling

For our standard, dashboard layout should be treated as a system: navigation, content width, secondary panels, mobile behavior, and focus movement are designed together.

### 3. Small reusable data-display patterns
Studio contains focused components such as SingleStat, TableRowNoResults, StateDot, SortDropdown, SortableSection, and VirtualizedTable.

Useful patterns:
- stat blocks have a clear label/value hierarchy and can optionally be interactive
- empty table states explain that the current search/filter returned no results
- status indicators have a dedicated semantic component rather than relying on arbitrary decoration
- sorting is an explicit interaction, not hidden behavior
- large tables can use virtualization instead of rendering every row

### 4. Keyboard-aware tooltips
ShortcutTooltip combines an existing interactive element with a tooltip and visible keyboard shortcut. The wrapped element remains the actual interactive control.

Rule for our projects:
- tooltips may add context, shortcuts, or explanations
- do not replace the accessible name with a tooltip
- icon-only controls still need an accessible name
- tooltip wrappers must not break click/focus/keyboard behavior

### 5. Data-heavy table behavior
VirtualizedTable separates scrolling, virtualization, row identity, empty content, leading/trailing content, and sticky headers. This is a useful architecture reference for dense operational tables.

Use virtualization only when dataset size or rendering cost justifies it; do not add complexity to small tables.

### 6. Accessibility is part of the shell
The Studio layout includes a skip link and a focusable main region. This reinforces that accessibility is not a final visual pass: navigation, focus order, keyboard interaction, and responsive shell behavior belong to the base layout.

## What we do NOT copy
- Supabase's React/Tailwind source code
- its exact colors, typography, spacing, or branding
- its application-specific state architecture
- its dependency choices when the destination environment differs
- dashboard code directly into WordPress

The destination implementation must follow its own theme/builder and the isolation rules in this repository.

## Best fit in our workflow
Use this reference when designing SaaS dashboards, admin panels, analytics/report pages, data tables, settings screens, navigation shells, stat cards, filters, or keyboard-heavy interfaces.

For current dependency/API details, continue to use Context7. For evidence-oriented operational states, combine this reference with guidelines/operational-data-ui.md and references/strix.md.