# System Capabilities

## What this system provides

This repository is a reusable design-and-development system for websites, web applications, SaaS products, dashboards, and application interfaces.

A developer should be able to understand the available capabilities quickly from this document.

## 1. Product and UX analysis

- Requirement and goal analysis
- Information architecture
- User flow and screen flow
- Primary/secondary action mapping
- Modal, drawer, dropdown, form, table, and detail flows
- Responsive/mobile behavior planning
- Analysis of existing UI and visual references
- Screenshot-to-Code prototyping
- Design-system extraction from evidence

## 2. UI and design system

- Typography rules
- Spacing and alignment
- Semantic color roles
- Borders, radius, shadows
- Reusable component patterns
- Component states
- Responsive breakpoints
- Evidence-based design-system decisions
- Avoiding accidental local patterns becoming global rules
- UI quality review
- Dashboard/data UI standards
- Operational data UI standards

## 3. Architecture and engineering

- Frontend/backend/API boundary definition
- Authentication and authorization boundaries
- Persistence and external-service boundaries
- Architecture and stack comparison
- System design and scalability planning
- Workload, concurrency, latency, data-volume, availability, security, and cost considerations
- Stateless application design where practical
- Failure-boundary and single-point-of-failure analysis
- Database architecture and access-pattern analysis
- Transaction and locking decisions
- Queue/background-processing decisions
- Rate limiting
- Health/readiness checks
- Design-pattern selection based on real problems
- Modular architecture and maintainability guidance
- Legacy modernization and incremental migration

## 4. API and data

- API/data-contract planning
- Pagination
- Payload minimization
- Input validation
- HTTP status-code conventions
- API versioning when compatibility requires it
- Loading/live/completed states
- Empty/no-results states
- Unavailable/partial/error states
- Filtered or changed-dataset handling
- Modal/detail synchronization
- Stale asynchronous response handling
- Summary/list/filter/detail consistency

## 5. Database and scalability

- Query and access-pattern analysis
- Indexing guidance
- N+1 detection
- Connection-pooling considerations
- Caching decisions
- Replication/partitioning/sharding decisions when justified
- Vertical vs horizontal scaling
- Load balancing decisions
- Infrastructure complexity control
- Performance bottleneck analysis

## 6. Frontend performance

- Bundle-size awareness
- Code/resource lazy loading when justified
- Asset and image optimization
- Avoiding unnecessary client-side work
- Dependency control
- CDN consideration when justified
- End-to-end performance thinking from browser to database and external services

## 7. Accessibility and responsive behavior

- Desktop/tablet/mobile review
- Responsive layout and navigation
- Typography and wrapping
- Cards, grids, tables, forms, and overflow
- Touch targets
- Keyboard access
- Focus behavior and restoration
- Semantic HTML
- Accessible names
- Reduced-motion behavior
- Mobile navigation and safe interaction patterns

## 8. Implementation standards

- Scoped CSS
- CSS isolation/namespacing
- Scoped JavaScript
- Justified component reuse
- Real data-model integration
- Explicit UI states
- WordPress/theme/builder-aware implementation
- Clean-up and review of AI-generated code
- Avoiding unnecessary dependencies

## 9. Browser QA and visual QA

- Real-browser validation with Playwright CLI
- Screenshots
- DOM/accessibility snapshots
- Locator and interaction testing
- Console inspection
- Network/request inspection
- Trace and video when needed
- Responsive/device testing
- Visual comparison against reference/intended design
- Iterative fix → recapture → compare workflow

## 10. Operations and production readiness

- Observability planning
- Actionable latency/error/resource signals
- Database and queue monitoring considerations
- Third-party dependency monitoring
- CI/CD
- Automated checks
- Deployment reproducibility
- Rollback strategy
- Staged/blue-green/canary deployment when justified
- Security architecture
- HTTPS
- Secure session handling
- Secret management
- Least privilege
- Rate limiting

## 11. Technical references and ecosystem guidance

The system includes reusable guidance for:

- Context7
- Playwright CLI
- React
- Vue
- Tailwind CSS
- Astro
- WordPress
- RealWorld architecture comparison
- System Design Primer
- Design Patterns
- Supabase
- Strix-derived operational UI patterns
- UI Skills
- Design Resources for Developers
- Free-for-Dev infrastructure discovery

These references are guidance sources, not requirements to use the referenced technologies.

## 12. Platform-specific support

Supported workflow targets include:

- Standard websites
- Web applications
- SaaS products
- Dashboards
- Application interfaces
- Responsive/mobile web
- WordPress
- Elementor
- Kadence
- Gutenberg
- Flatsome
- Custom stacks

## 13. Documentation

The system can record:

- Technology and environment
- Architecture decisions
- Design decisions
- Constraints
- Reference sources
- QA viewports
- Known limitations
- Implementation notes
- Project-specific decisions and QA records

## End-to-end capability

The complete reusable process is:

**Requirements / Reference → Product & UX Analysis → Information Architecture → UI Analysis → Prototype / Design System → Architecture & Stack → Pattern Selection → Technical Verification → Implementation → Data/API States → Performance / Security / Operations → Responsive & Accessibility → Browser QA → Visual QA → Refinement → Documentation**

## Important rule

This system is a decision framework, not a checklist for adding complexity. A capability or reference is used only when it solves a real project requirement.

Last reviewed: 2026-09-29
