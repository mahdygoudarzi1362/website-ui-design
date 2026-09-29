# React

Source: [facebook/react](https://github.com/facebook/react)

## Role in this system

React is a component-based implementation option for interactive web interfaces and application UIs.

The repository is a **framework/library reference**, not a requirement to use React.

## Reusable principles

- Model UI as reusable components with clear responsibilities and predictable data flow.
- Keep component boundaries aligned with actual UI behavior and reuse; do not split code merely for abstraction's sake.
- Treat loading, empty, error, unavailable, and interaction states as part of the component contract.
- Keep visual styling and behavior scoped to the component/system that owns them.
- Prefer the project's established state/data approach instead of introducing unnecessary global state.
- Verify the exact React and related-library versions and APIs against current documentation before production implementation.
- Test the rendered result in a real browser at relevant viewports.

## When to use

Use this reference when a project uses React or when component architecture, stateful UI, or reusable interactive application interfaces are being designed.

Last reviewed: 2026-09-29
