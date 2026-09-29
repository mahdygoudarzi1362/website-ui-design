# Website UI Design

A reusable standard for designing and developing web pages, web applications, dashboards, and application interfaces—from requirements or visual references through implementation, browser QA, and refinement.

The repository is intentionally broader than a UI/UX checklist: it is a reusable design-and-development playbook for real web and app interfaces.

## Purpose

This repository is independent of AnalysData and independent of the destination website's GitHub connection. It stores reusable workflow, guidelines, references, and project documentation for website UI work.

## Standard workflow

The workflow starts from whichever input the project has: requirements, user flows, an existing interface, a screenshot/Figma reference, or a working page.

Requirements/reference → information architecture and flow → UI analysis → prototype/design system → current library/API verification → implementation → data/API and interaction states → responsive/accessibility → browser QA with Playwright → visual QA → compare, refine, and document.

For WordPress and screenshot-driven work, use the specialized workflow in `workflow/screenshot-to-wordpress.md`.

## Core principles

- Screenshot-to-Code is a prototype generator, not the production architecture.
- Current library/API documentation is verified before relying on versioned APIs.
- UI quality is checked with focused, task-specific rules rather than one giant checklist.
- AI-generated code must be reviewed and cleaned before production use.
- CSS must be isolated/namespaced to avoid theme and plugin conflicts.
- JavaScript must be scoped to the component or feature.
- Responsive behavior is part of the design, not a final afterthought.
- Accessibility and motion performance are part of UI QA.
- Data-heavy UI must model loading, live, completed, empty, unavailable, partial, and error states explicitly when applicable.
- Summary counts, lists, filters, and detail views must correspond to the same underlying dataset.
- Findings should expose evidence and meaningful status/severity rather than only decorative labels.
- Product/dashboard UI should use semantic visual roles and reusable data primitives rather than scattered one-off styling.
- Dashboard shells should treat navigation, responsive behavior, focus, empty states, and dense data presentation as one system.
- Design-system rules require evidence; accidental local patterns are not automatically promoted to global rules.
- The installed result must be checked in a real browser when possible, using screenshots and interaction evidence rather than assumptions.
- The workflow supports websites, web applications, SaaS dashboards, application interfaces, and responsive/mobile web experiences.
- WordPress, Elementor, Kadence, Gutenberg, Flatsome, and custom stacks are supported integration targets.
- The destination site does not need to be connected to GitHub.

## Capability map

For a fast overview of everything this system provides, see [`CAPABILITIES.md`](CAPABILITIES.md).

## General development workflow

For a new website, SaaS page, dashboard, or application interface, start with `workflow/web-app-development.md`. Use platform-specific workflows only when their constraints apply.

## Repository structure

- workflow/ — end-to-end workflows for different project types
- references/ — tools, frameworks, and technical/design references
- guidelines/ — implementation and QA rules
- projects/ — project-specific decisions and QA records
