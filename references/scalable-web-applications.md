# Scalable Web Application Practices

Source reviewed:
- Ripenapps Technologies, "Building Scalable Web Applications: Best Practices for Modern Development" (2026-06-17)

## Role in this system

Use this as a practical checklist for growth-oriented web applications. It complements the architecture decision guidance in `references/system-design-primer.md`; it is not a mandate to add distributed infrastructure.

## Architecture and scaling

- Start with the simplest architecture that satisfies current and reasonably expected requirements.
- Prefer modular boundaries and clear responsibilities so individual areas can evolve without a rewrite.
- Consider vertical scaling before introducing distributed complexity when the workload permits it.
- Use horizontal scaling, load balancing, shared state stores, queues, or replicas only when workload, availability, or failure requirements justify them.
- For every infrastructure component, record the problem it solves, its operational cost, failure mode, and recovery/monitoring path.

## API design

- Paginate large collections.
- Avoid unnecessary response payloads.
- Validate inputs consistently.
- Use meaningful HTTP status codes.
- Version externally consumed APIs when compatibility requires it.
- Move slow or non-user-blocking work to background processing when the workload and reliability requirements justify it.

## Database and caching

- Index according to real access patterns.
- Detect and remove N+1 query behavior.
- Use connection pooling within database limits.
- Optimize expensive queries before adding servers.
- Consider caching only for repeated access patterns where freshness and invalidation are understood.
- Treat replicas, partitioning, and sharding as workload-driven choices, not default scalability steps.

## Frontend performance

Treat performance as part of product quality across the whole request path.

- Control JavaScript bundle size.
- Lazy-load code or resources when it materially improves initial work.
- Optimize images and static assets.
- Avoid unnecessary client-side computation and dependencies.
- Use a CDN when geographic distribution or asset delivery warrants it.

## Deployment and DevOps

For systems where deployment risk matters:

- automate tests and relevant static checks;
- keep deployment steps reproducible;
- provide a rollback path;
- use infrastructure-as-code when infrastructure complexity justifies it;
- use staged, blue-green, or canary deployment only when the operational risk and environment warrant the added complexity.

CI/CD is an operational mechanism, not a goal by itself.

## Observability

Define actionable signals for:

- response latency;
- error rates;
- CPU/memory or other resource saturation;
- database performance;
- queue/background-job state;
- important third-party dependencies.

Use logs, metrics, and traces according to the diagnostic problem. Monitoring should support detection, diagnosis, and recovery rather than become telemetry for its own sake.

## Security

Scalability does not replace security. Treat these as architecture concerns:

- authentication and authorization;
- HTTPS;
- input validation;
- secure session handling;
- secret management/rotation;
- rate limiting;
- least privilege.

## Legacy modernization

For a working legacy application, avoid assuming a full rewrite is automatically safer.

Prefer incremental migration when appropriate:

- expose stable functionality through clear boundaries;
- migrate one responsibility/module at a time;
- replace outdated dependencies deliberately;
- keep rollback and coexistence paths explicit;
- validate each migrated boundary before moving the next one.

## Practical review questions

Before launch or a major growth phase:

1. Where is the current bottleneck likely to appear first?
2. Which data sets need pagination?
3. Which queries are expensive or repeated?
4. What state must be shared between application instances?
5. Which work can safely become asynchronous?
6. What happens when a database, queue, external API, or application instance fails?
7. Which production signals would reveal the problem quickly?
8. How is a bad deployment rolled back?
9. Which security controls protect the new surface area?
10. What can be migrated incrementally instead of rewritten?

## Important boundary

Do not turn this checklist into automatic infrastructure. Measure the workload, identify the actual constraint, and add complexity only when its benefit is clear.

Last reviewed: 2026-09-29
