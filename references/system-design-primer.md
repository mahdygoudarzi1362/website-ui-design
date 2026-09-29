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

## Database architecture principles

Use the database section of the source as a decision framework, not as a checklist for adding infrastructure.

- Start from access patterns, read/write workload, data volume, consistency, latency, and availability requirements.
- Choose relational or non-relational storage based on the data model and access patterns rather than popularity.
- Consider normalization first; introduce denormalization when a measured access pattern justifies the additional consistency and write complexity.
- Treat indexing, query design, connection limits, and transaction behavior as part of application architecture.
- Consider replication, partitioning/sharding, caching, and federation only when workload or availability requirements justify them.
- Make backup, recovery, migration, and failure behavior explicit for production data.
- Keep database boundaries and ownership clear when multiple services or application modules are introduced.
- Document important trade-offs between consistency, availability, latency, cost, and operational complexity.

Last reviewed: 2026-09-29
