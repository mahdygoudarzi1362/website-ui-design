# System Design Primer

Source: [donnemartin/system-design-primer](https://github.com/donnemartin/system-design-primer)

## Role in this system

This is an architecture reference for web applications that may need to scale beyond a simple single-process implementation.

## Reusable principles

- Define the system's workload, data flow, dependencies, and failure boundaries before selecting infrastructure.
- Keep application servers as stateless as practical; move shared sessions/state to appropriate persistent stores when needed.
- Treat databases, caches, queues, object storage, external APIs, and load balancers as explicit architectural dependencies.
- Identify single points of failure and understand the complexity introduced by redundancy.
- Scale only the bottleneck that the actual workload demonstrates; do not add distributed infrastructure speculatively.
- Separate functional requirements from non-functional requirements such as availability, latency, consistency, security, and cost.
- Design for observability and failure handling, not only the happy path.
- Architecture decisions should follow the product's expected traffic, data volume, concurrency, and operational constraints.

## When to use

Use this reference during architecture planning for SaaS, dashboards, APIs, multi-user applications, or migrations from a monolithic/shared-host setup to more scalable infrastructure.

Last reviewed: 2026-09-29
