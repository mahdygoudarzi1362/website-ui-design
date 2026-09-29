# UI Quality Guidelines

Use this as the default quality gate for generated or manually implemented UI.

## Baseline

Before final approval, review:

- visual hierarchy
- spacing consistency
- typography and line wrapping
- data and numeric alignment
- dense-content overflow
- loading states
- empty states and their next action
- icon-only controls and accessible names
- destructive or irreversible actions
- fixed elements and viewport-height behavior

## Visual restraint

Do not add visual effects merely to make a UI look impressive.

Unless the reference or product requirement explicitly calls for them:

- no gradients
- no glow as a primary affordance
- no unnecessary animation
- no arbitrary decorative effects
- do not introduce new accent colors when existing theme tokens are sufficient

Use the existing design system and component primitives before creating new ones.

## Motion

If animation is required:

- prefer transform and opacity
- avoid continuous animation of layout properties
- keep interaction feedback short
- respect prefers-reduced-motion
- pause looping animation when off-screen
- avoid large blur or backdrop-filter animation
- do not mix animation systems without a clear reason

Animation is optional. A static implementation is preferred when motion does not communicate state, hierarchy, or interaction.

## Accessibility

Verify at minimum:

- keyboard operation
- visible focus
- semantic buttons and links
- accessible names for icon-only controls
- labels for form controls
- errors shown near the relevant action/input
- correct dialog semantics for destructive actions
- accessible primitives used where the project already provides them

Do not hand-build keyboard/focus behavior when an established project primitive can provide it.

## Responsive behavior

Apply the existing responsive guideline, but also check:

- fixed elements against safe-area requirements
- mobile interaction targets
- dense data and truncation
- state changes caused by reduced width

## Final rule

A UI is not ready because it renders. It is ready when it is visually coherent, isolated, responsive, accessible, and free of unnecessary visual or runtime complexity.
