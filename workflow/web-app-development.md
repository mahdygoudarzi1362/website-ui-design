# Web & App Design and Development Workflow

## Purpose

Use this workflow when developing a web page, web application, SaaS interface, dashboard, or application UI from requirements, an existing product, a visual reference, or a combination of them.

This is the general workflow. Specialized workflows can add platform-specific steps.

## 1. Understand the product and page

Define:
- user goal
- page or screen purpose
- primary actions
- information hierarchy
- required data and integrations
- success, empty, loading, error, unavailable, and partial states when applicable
- technical constraints and target platform

Do not start from visual styling alone when the page has product or operational behavior.

## 2. Map structure and flow

Define the information architecture and relevant user flow:
- navigation
- sections/screens
- entry and exit points
- primary and secondary actions
- modal, drawer, dropdown, form, table, or detail flows
- responsive/mobile behavior

For multi-screen applications, treat the shell, navigation, and shared interaction patterns as a system.

## 3. Analyze references and existing UI

When references exist, inspect:
- layout and hierarchy
- spacing and alignment
- typography
- color and semantic visual roles
- components
- imagery and assets
- interaction cues
- responsive behavior

Do not copy accidental local patterns into a global design system without evidence.

## 4. Prototype and establish the design system

Use Screenshot-to-Code or another appropriate prototyping method when useful.

Establish only the design rules supported by the product/reference:
- typography
- spacing
- colors and semantic roles
- borders/radius/shadows
- component patterns
- states
- responsive breakpoints

Prototype code is not automatically production architecture.

## 5. Architecture and stack boundaries

Before implementation, make the main technical boundaries explicit:

- Separate product requirements and user flows from the framework or language used to implement them.
- Identify frontend, backend/API, authentication, persistence, external services, deployment, and operational dependencies.
- For multi-user or growing applications, record expected traffic, concurrency, data volume, latency, availability, security, and cost constraints.
- Keep application state as local or stateless as practical; introduce shared stores, caches, queues, or other infrastructure only when the requirements justify them.
- Identify single points of failure and important failure boundaries.
- Compare alternative implementations by behavior, responsibility, operational cost, and maintainability rather than syntax or popularity.
- Do not copy demo-project architecture into production without validating its scale, security, performance, and maintenance requirements.

Use references/realworld.md for cross-stack implementation comparison and references/system-design-primer.md for architecture/scalability decisions.

## 5. Verify the technical environment

Before relying on framework, UI-library, chart, icon, animation, API, or other versioned behavior:
- identify the actual target environment
- verify current documentation with Context7 when applicable
- respect the project's pinned versions
- avoid introducing dependencies without a reason

## 6. Implement the real interface

Build against the actual target stack.

Keep:
- CSS scoped and isolated where needed
- JavaScript scoped to the feature
- components reusable when reuse is justified
- semantics and accessible names intact
- data presentation tied to the real data model
- states explicit rather than implied by blank space

For WordPress, adapt to the active theme/builder instead of blindly pasting prototype code.

## 7. Implement behavior and data states

For interactive or data-driven interfaces, verify:
- loading
- live/in-progress
- completed/success
- empty
- no results
- unavailable
- partial
- error
- filtered or changed dataset
- modal/detail synchronization
- stale async response handling where relevant

Summary counts, lists, filters, selections, and details must represent the same underlying dataset.

## 8. Responsive and accessibility pass

Check desktop, tablet, and mobile as applicable:
- layout
- navigation
- typography and wrapping
- grids/cards/tables
- buttons and forms
- overflow
- fixed/sticky elements
- modal/dropdown behavior
- touch targets and mobile interaction

Also check keyboard access, focus behavior, semantics, accessible names, and reduced-motion behavior when relevant.

## 9. Browser QA

Use Playwright CLI when a real browser is available.

Capture evidence appropriate to the problem:
- screenshots for visual correctness
- snapshots for structure and interaction targets
- console/network evidence for runtime problems
- trace/video for complex timing or multi-step failures

A successful click or page load does not by itself prove visual correctness.

## 10. Visual QA and refinement

Compare the rendered result against the approved reference or intended design.

Prioritize:
1. overall layout and dimensions
2. positioning and spacing
3. typography and wrapping
4. components and visual details
5. colors, borders, shadows, and imagery
6. responsive behavior

Fix the smallest relevant problem, rerun the affected checks, and capture new evidence.

## 11. Document the result

For reusable or significant projects, record:
- technology/environment
- important design decisions
- constraints
- reference sources
- QA viewports
- known limitations
- final implementation notes

## Platform-specific extensions

- WordPress: workflow/screenshot-to-wordpress.md
- Browser QA: guidelines/browser-qa.md
- Visual comparison: guidelines/visual-comparison.md
- Dashboard/data UI: guidelines/dashboard-ui.md and guidelines/operational-data-ui.md

The same general workflow can be adapted to websites, SaaS products, web applications, dashboards, and application interfaces without requiring the destination project itself to be connected to GitHub.
