# Website UI Design

A reusable standard for website UI design and implementation, especially when starting from screenshots or visual references.

## Purpose

This repository is independent of AnalysData and independent of the destination website's GitHub connection. It stores reusable workflow, guidelines, references, and project documentation for website UI work.

## Standard workflow

Screenshot/reference → UI analysis → prototype with Screenshot-to-Code → current library/API verification → UI baseline and evidence review → clean/review code → WordPress-ready implementation → CSS/JS isolation → responsive implementation → install on the real site → visual QA → compare and refine.

## Core principles

- Screenshot-to-Code is a prototype generator, not the production architecture.
- Current library/API documentation is verified before relying on versioned APIs.
- UI quality is checked with focused, task-specific rules rather than one giant checklist.
- AI-generated code must be reviewed and cleaned before production use.
- CSS must be isolated/namespaced to avoid theme and plugin conflicts.
- JavaScript must be scoped to the component or feature.
- Responsive behavior is part of the design, not a final afterthought.
- Accessibility and motion performance are part of UI QA.
- Design-system rules require evidence; accidental local patterns are not automatically promoted to global rules.
- The installed result must be checked against the reference visually.
- The workflow supports WordPress, Elementor, Kadence, Gutenberg, Flatsome, and custom sites.
- The destination site does not need to be connected to GitHub.

## Repository structure

- workflow/ — end-to-end workflows
- references/ — tools and technical references
- guidelines/ — implementation and QA rules
- projects/ — project-specific decisions and QA records
