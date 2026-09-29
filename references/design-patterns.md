# Design Patterns Reference

Source: [DovAmir/awesome-design-patterns](https://github.com/DovAmir/awesome-design-patterns)

## Role in this system

Use design patterns as reusable solutions to recurring design problems, not as mandatory structures. Select a pattern because it clarifies a real responsibility, dependency, state transition, integration boundary, or variation point.

## Practical rules

- Start with the product requirement, data flow, and responsibility boundary; choose a pattern afterward.
- Prefer the simplest design that keeps responsibilities clear.
- Do not introduce a pattern only because it is familiar, popular, or listed in a catalog.
- Avoid speculative abstractions and premature indirection.
- When a pattern is used, document the problem it solves and the trade-off it introduces.
- Keep framework-specific patterns separate from general application/domain patterns.
- Treat architectural patterns such as modular monolith, hexagonal/ports-and-adapters, event-driven, CQRS, and microservices as architectural choices, not interchangeable coding recipes.
- For frontend work, patterns should preserve component responsibility, predictable state/data flow, accessibility, and testability.
- For backend work, patterns should preserve clear boundaries between transport/API, application logic, domain behavior, persistence, and external integrations.
- Reassess a pattern when requirements, scale, or operational constraints change.

## Pattern selection questions

Before introducing a pattern, answer:

1. What recurring problem are we solving?
2. Which responsibility or dependency is difficult to change?
3. What simpler implementation was considered?
4. What complexity does the pattern add?
5. How will we verify that the pattern is helping?

## Useful pattern areas

For this playbook, the most relevant categories are:

- object/component collaboration
- dependency inversion and composition
- state and behavior management
- application/service boundaries
- repository and persistence boundaries
- adapter/integration boundaries
- event and message handling
- modular monolith boundaries
- frontend component and state patterns
- API and distributed-system patterns

Do not import language-specific implementations directly into another stack. Translate the underlying responsibility and trade-off to the target technology.

## When to use

Use this reference when implementation has recurring coupling, variation, state, integration, or responsibility-boundary problems that simple composition does not resolve.

Last reviewed: 2026-09-29
