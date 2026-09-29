# UI Skills

Official project: https://github.com/ibelick/ui-skills

UI Skills is a collection of focused skills for design-engineering work. In this repository it is used as a design and QA reference, not as a dependency or source-code library.

## What we adopt

### 1. Small, task-specific review context

Do not apply a large UI checklist to every task.

Select the smallest useful review context:
- baseline visual cleanup
- accessibility
- motion performance
- design-system extraction/documentation
- broader UI improvement review

Prefer one focused skill; use two when two distinct concerns are required. Use a broader review only when the task genuinely spans multiple surfaces.

### 2. Baseline UI quality

Before accepting AI-generated UI, review:
- spacing and visual hierarchy
- typography and line wrapping
- data alignment and numeric presentation
- loading and empty states
- icon-only control labels
- destructive-action confirmation
- viewport-height behavior
- safe-area behavior for fixed controls
- unnecessary visual effects

Avoid adding animation, gradients, glow, or decorative effects unless they serve an explicit design requirement.

### 3. Motion rules

When motion exists:
- prefer transform and opacity
- do not continuously animate layout properties
- avoid scroll-event-driven animation when a browser-native or observer-based approach works
- keep interaction feedback short
- pause off-screen looping motion
- respect prefers-reduced-motion
- avoid large blur/backdrop-filter animation
- do not mix animation systems casually

### 4. Accessibility rules

Accessibility is part of UI QA, not a separate afterthought.

At minimum verify:
- keyboard and focus behavior
- accessible names for icon-only controls
- semantic interactive elements
- visible focus states
- form labels and error proximity
- appropriate dialog semantics for destructive actions
- no custom replacement for established accessible primitives when a suitable project primitive exists

### 5. Evidence before design-system rules

Do not turn one local implementation into a global design rule.

A design rule should be supported by:
- an existing documented decision, or
- a named shared token/primitive/variant used by the relevant surfaces, or
- repeated rendered evidence when reconstructing a system from a live site.

Prefer existing owners and tokens over inventing new ones.

### 6. UI improvement review

When reviewing an existing surface:
1. trace the actual rendered path
2. identify the design evidence that governs it
3. verify the runtime relationship
4. identify one deterministic correction
5. try to falsify the finding before reporting it

Search results, repeated class names, or visual preference alone are not enough to declare a design-system violation.

## What we do not copy

This repository does not copy UI Skills' CLI, MCP server, agent files, or framework-specific dependencies. The target workflow remains compatible with WordPress, HTML/CSS, builders, and other environments.

## License

UI Skills is MIT licensed. This reference records the adopted workflow principles rather than redistributing the source skill files.
