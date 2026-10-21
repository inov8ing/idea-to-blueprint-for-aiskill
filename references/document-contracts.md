# Contracts for the Six Required Documents

All six documents should be usable by product, design, engineering, QA, and operations. Use concise, specific language; tables are appropriate for structured requirements. Every document includes title, status (`Draft`, `Proposed`, `Approved`, `Superseded`), version/date, owner role, source links, assumptions, decision IDs, and change notes.

## 1. PRD — `01-PRD.md`

Must include:
- Executive product summary and problem statement.
- Target audiences/personas and context of use.
- User needs/jobs, existing workaround, value proposition.
- Goals and measurable success metrics (formula, baseline, target, time period, instrumentation needs).
- Non-goals and explicit out-of-scope items.
- Functional requirements with stable IDs such as `REQ-001`, priority, actor, rationale, preconditions, expected behavior, acceptance criteria, error/edge cases, and dependencies.
- User stories only when useful; never let “As a user...” text replace testable rules.
- Non-functional requirements with measurable or verifiable targets where possible.
- Business rules, roles/permissions, content and localization requirements.
- Analytics/feedback/support expectations if in scope.
- Risks, assumptions, unresolved decisions, release criteria, launch constraints.
- Traceability into journeys, screens, data/API contracts, milestones and tests.

Requirement quality: singular, unambiguous, feasible, necessary, testable, prioritized. A requirement should not combine unrelated outcomes. Use `TBD` with an owner/date rather than fake precision.

## 2. TRD — `02-TRD.md`

Must include:
- System context and current vs proposed architecture.
- Constraints and architecture drivers sourced from the brief.
- Stack selection rationale: viable options, trade-offs, ecosystem maturity, platform fit, hosting/distribution, developer capabilities, costs/operational burden, and reason for choice. Research changing claims with primary sources where available.
- Component/service boundaries and responsibilities.
- Runtime and data-flow diagrams; interfaces and API/event contracts with auth, validation, error behavior and versioning as relevant.
- Local/cloud/offline model, deployment topology, environments, configuration/secrets strategy.
- Security/privacy threat considerations, access control, encryption needs, data minimization and retention.
- Performance, reliability, observability/logging/metrics, accessibility/compatibility, scalability only to the needed degree.
- Backup/restore, migrations, upgrade, rollback, failure handling, external dependency strategy.
- Build/test/release pipeline and operational ownership.
- Alternatives and Architecture Decision Records/`DEC-###` references.
- Unknowns and validation spikes/prototypes needed before committing.

Don't prescribe microservices, Kubernetes, event sourcing, AI, a server backend, or a cloud service by fashion alone. Optimize for requirements and total complexity.

## 3. Appflow / User Journeys — `03-APPFLOW-USER-JOURNEYS.md`

Must include:
- Personas/roles and entry conditions.
- Information architecture/navigation model.
- Main end-to-end journeys with stable IDs such as `JNY-001`.
- Each journey's goal, trigger, prerequisites, numbered user/system steps, decision branches, expected end state, persisted state, analytics/success signal, failure routes, cancellation, retry, recovery, and permission boundaries.
- First run/onboarding, returning use, important secondary tasks, account recovery, settings, export/delete/support flows where applicable.
- Empty/loading/progress/error/partial-success behavior.
- Mermaid flowcharts or equivalent diagrams plus text narrative.
- Links to requirements and screen IDs. Clearly label decisions that need product-owner input.

A happy-path-only diagram is incomplete. Include failure and recovery routes for critical actions, and do not draw flows that the requirements or architecture cannot support.

## 4. UI/UX Design Specification — `04-UI-UX-DESIGN-SPEC.md`

Must include:
- UX principles tied to the product context (not generic slogans).
- Brand/product voice, content hierarchy and writing style; sample exact labels/messages where useful.
- Information architecture, screen/page inventory with stable IDs such as `SCR-001`.
- Primary task layouts, hierarchy, navigation, responsive behavior and platform conventions.
- Main components, variants and interaction states.
- Forms, constraints, validation, success/error copy, destructive confirmation, undo/recovery.
- Loading, empty, first-use, offline, permission denied, stale data, timeout and partial-failure states as relevant.
- Accessibility: semantics, labels, keyboard/focus order, contrast, zoom/text scaling, reduced motion, touch target and screen-reader considerations.
- Design token direction: color roles, typography, spacing, density, shape, elevation, icon use, focus treatment; include actual values when known or mark proposed.
- Responsive breakpoints/layout behavior derived from supported platforms, not arbitrary values presented as fact.
- Localization, date/time/number formats, RTL or language requirements where relevant.
- Design reference inventory with what to borrow/avoid and reasons.
- Usability test questions and validation tasks.

Humanized UX requires concrete user context and useful copy, not random emojis, excessive cards/gradients, chatbots by default, or a visual style detached from the product. Do not claim to have supplied Figma files, images, prototypes or rendered screens unless those artifacts exist.

## 5. Backend / Data Schema — `05-BACKEND-DATA-SCHEMA.md`

First section must state one of: `Server backend required`, `Local-first data model`, `Static/no persistent data`, or `Needs decision`, with rationale.

When applicable, include:
- Entity/collection/table inventory and stable IDs such as `ENT-001`.
- Field name, type, required/optional, defaults, constraints, sensitivity classification, validation, and lifecycle.
- Primary/foreign keys, cardinality, unique constraints, indexes and soft/hard delete policy.
- Ownership, tenant boundaries, roles and authorization rules.
- Relationships and ER diagram.
- Example safe synthetic records.
- API endpoints or commands/events with request/response schemas, validation, auth, errors, idempotency and pagination where relevant.
- Transaction boundaries, concurrency/conflict resolution, deduplication, file/object storage, background processing and queues only when needed.
- Retention, export/deletion, audit trail, backup/restore and migration strategy.
- Data integrity invariants and tests.
- Separation between domain model, persistence model and transport DTOs where warranted.

Never embed production secrets or real personal data. Do not invent columns because a generic template expects them. Align all fields and operations with real requirements and journeys.

## 6. Implementation Plan — `06-IMPLEMENTATION-PLAN.md`

Must include:
- Scope baseline and links to decisions/requirements.
- Milestones, goals and acceptance/exit gates.
- Dependency graph and sequencing rationale.
- Work packages/tasks mapped to requirement, journey, screen, entity/API and test IDs.
- Ownership/role, prerequisites, deliverables, risks, estimates or ranges, confidence, and measurable completion criteria.
- Architecture validation spikes for costly or high-risk unknowns before building dependent features.
- Thin vertical slices and demo-able increments.
- Development environment, branching/PR/review, CI, formatting/linting/type-checking, test levels, test data and environment strategy.
- Security/privacy, accessibility, compatibility, observability, performance and recovery work where applicable.
- Documentation, support, release, rollback, migration, closed testing and post-release feedback.
- Definition of done, decision gates, sign-off responsibilities and contingency plan.
- Explicit exclusions and conditions that would change the plan.

A task such as “build backend” is too broad. Decompose into end-to-end outcomes, interfaces, migrations, validation and tests. Do not place all tests at the end.

## Shared language and traceability

Suggested IDs: `OUT-###` outcome, `REQ-###` requirement, `NFR-###` quality attribute, `JNY-###` journey, `SCR-###` screen, `ENT-###` entity, `API-###` interface, `DEC-###` decision, `RISK-###` risk, `MS-###` milestone, `TST-###` verification case.

Use the same ID for the same concept across all documents. The traceability matrix should show uncovered requirements and orphan UI/schema/tasks. IDs should be stable across edits; do not renumber everything just to make numbering look tidy.
