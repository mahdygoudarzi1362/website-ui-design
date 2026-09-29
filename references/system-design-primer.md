# System Design Reference

Sources:
- [donnemartin/system-design-primer](https://github.com/donnemartin/system-design-primer)
- [casp3ro/system-design](https://github.com/casp3ro/system-design)

## Role in this system

These are architecture references for web applications that may need to scale beyond a simple single-process implementation. Use them as decision frameworks, not templates to copy.

## Requirements and workload first

Before choosing architecture or infrastructure:

- Define users, primary use cases, inputs, outputs, and functional boundaries.
- Separate crucial first-release requirements from optional enhancements.
- Record expected total users, active users, peak concurrent users, request volume, read/write ratio, latency, throughput, data ingestion, storage growth, retention, and bandwidth when these materially affect architecture.
- Separate functional requirements from non-functional requirements such as availability, latency, consistency, security, reliability, and cost.
- State assumptions explicitly when measurements are unavailable; replace them with observed data as the system matures.

## Reusable architecture principles

- Define the system's workload, data flow, dependencies, and failure boundaries before selecting infrastructure.
- Keep application servers as stateless as practical; move shared sessions/state to appropriate persistent stores when needed.
- Treat databases, caches, queues, object storage, external APIs, and load balancers as explicit architectural dependencies.
- Identify single points of failure and understand the complexity introduced by redundancy.
- Scale only the bottleneck that the actual workload demonstrates; do not add distributed infrastructure speculatively.
- Design for observability and failure handling, not only the happy path.
- Architecture decisions should follow the product's expected traffic, data volume, concurrency, and operational constraints.

## Database architecture principles

Use the database guidance as a decision framework, not as a checklist for adding infrastructure.

- Start from access patterns, read/write workload, data volume, consistency, latency, and availability requirements.
- Choose relational or non-relational storage based on the data model and access patterns rather than popularity.
- Consider normalization first; introduce denormalization when a measured access pattern justifies the additional consistency and write complexity.
- Treat indexing, query design, connection limits, and transaction behavior as part of application architecture.
- Consider replication, partitioning/sharding, caching, and federation only when workload or availability requirements justify them.
- Make backup, recovery, migration, and failure behavior explicit for production data.
- Keep database boundaries and ownership clear when multiple services or application modules are introduced.
- Document important trade-offs between consistency, availability, latency, cost, and operational complexity.

## API and component boundaries

- Define the main API operations and data contracts before implementation when a separate frontend/backend boundary exists.
- Keep authentication/authorization, business logic, persistence, and external integrations as explicit responsibilities.
- Use queues/background processing for work that does not need to block the user-facing request when justified by workload and reliability requirements.
- Use rate limiting where abuse or traffic bursts can threaten service stability.
- Define health checks for services where deployment/orchestration needs to distinguish a running process from one ready to receive traffic.
- Treat optimistic/pessimistic locking and transaction boundaries as explicit choices when concurrent writes can conflict.

## Reliability and scaling

- Prefer the simplest architecture that satisfies the measured requirements.
- Consider vertical scaling before introducing distributed complexity when the workload permits it.
- Introduce replicas, caches, queues, sharding, load balancing, or multi-region deployment only when their benefits justify their operational cost.
- For every additional infrastructure component, document the problem it solves, its failure mode, and how it is monitored and recovered.
- Consider network latency and geographic distribution when users or services are regionally separated.

## When to use

Use these references during architecture planning for SaaS, dashboards, APIs, multi-user applications, database design, or migrations from a monolithic/shared-host setup to more scalable infrastructure.

Last reviewed: 2026-09-29
