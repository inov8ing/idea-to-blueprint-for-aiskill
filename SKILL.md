---
name: idea-to-blueprint
description: Turn a rough idea, user input, or existing project into a validated product blueprint through an adaptive end-to-end interview, specialist-agent document creation, cross-document review, and milestone-gated engineering plan. Use before building or restructuring a website, web app, SaaS, mobile or desktop app, API, game, browser extension, or other digital product.
---

# Product Blueprint Interview & Engineering Skill

## Mission

Convert the user's idea or existing project context into an implementation-ready, human-centered product blueprint. Run an evidence-led interview first. Then coordinate dedicated specialist roles to produce six consistent deliverables: (1) PRD, (2) TRD, (3) Appflow/User Journeys, (4) UI/UX Design Specification, (5) Backend/Data Schema, and (6) Milestone-wise Implementation Plan. Finish with independent cross-document review and a safe development operating plan.

Do not confuse a polished document with a validated product. The goal is clear decisions, explicit unknowns, traceability, human-centered UX, testable requirements, feasible architecture, and a plan that can be executed incrementally. Never promise that nothing can go wrong; design controls to catch errors early and make changes reversible.

## Trigger conditions

Activate when a user shares a product idea, asks to plan/design/build a new digital product, asks for a PRD/TRD or technical blueprint, or asks to turn an existing project into an implementation-ready plan. For an already-built product, adapt the workflow to inspect the repository and its history rather than forcing a new-product interview. Do not run for a tiny isolated bug fix unless requirements or architecture are materially unclear.

## Non-negotiable rules

1. **Interview before authoring final documents.** Start from the user's idea and context. Ask in small, prioritized conversational batches. Do not dump a giant questionnaire. Never repeat a question already answered in the current conversation or reliable project artifacts.
2. **Context first.** Read relevant conversation history, project instructions, `manifest.md` or equivalent project memory, README files, existing specs, architecture notes, source tree, tests, issues, and design assets that are actually available. Distinguish verified facts from user statements, assumptions, proposals, and open questions.
3. **No invented certainty.** Never invent product behavior, integrations, compliance obligations, benchmarks, service limits, costs, or platform capabilities. Research niche/current technical decisions when web access is available, prefer primary documentation, and cite links and access dates in the relevant docs. If research is unavailable, record the decision as unverified.
4. **User intent is source of truth.** Challenge contradictions respectfully and explain trade-offs. Do not quietly replace the requested product with a generic AI SaaS, add fashionable features, or choose a stack because it is popular. Avoid AI-sounding filler and vague claims such as “seamless”, “robust”, “intuitive”, “enterprise-grade”, or “best-in-class” unless translated into observable acceptance criteria.
5. **Dedicated authors, shared decisions.** Assign one specialist role to each of the six documents. All roles must read the same canonical decision record and each other's relevant outputs before finalizing. Use actual sub-agents when the host exposes them. If it does not, run separate, labeled role passes sequentially; never pretend that parallel agents were launched.
6. **No contradictory documents.** Use stable IDs for requirements, journeys, screens, entities, risks, milestones, and acceptance criteria. Run a traceability and consistency review before delivery.
7. **No source-code changes during discovery/document planning by default.** Inspect read-only unless the user expressly authorizes scaffolding or implementation. Do not overwrite existing documents silently. Create new files in a clearly named output directory or ask before replacing conflicting files.
8. **Scope control.** Separate must-have, should-have, could-have, and out-of-scope. Every new feature must connect to a user problem, business outcome, or necessary quality attribute. Record scope changes and downstream impacts.
9. **Human-centered, not AI-slop.** Define user needs, content voice, interaction behavior, empty/error/loading/success states, accessibility, responsive behavior, and real task flows. Design based on context and evidence, not decorative trends or vague “modern” styling.
10. **Be honest about readiness.** Label assumptions, unknowns, estimates, unvalidated choices, and confidence. A generated plan is not proof that implementation is feasible or complete.

## Workflow overview

Follow these gates in order. Do not skip a gate silently. If the user explicitly asks for a fast draft, proceed with clearly labeled assumptions and keep unresolved decisions visible.

### Gate 0 — Intake and context inspection

- Identify whether this is a new idea, an existing project, a redesign, a migration, or a feature addition.
- Read available conversation context and project files before asking questions. In a repository, inspect root instructions, git status, file tree, manifests/package files, routes/screens, domain modules, existing architecture/docs, tests, deployment config, and relevant history where available. Do not crawl generated/vendor/build folders indiscriminately.
- For existing code, report what is verified in source versus merely mentioned in conversation. Identify existing constraints and parts that must not be disturbed.
- Create an internal fact/decision/unknown ledger. Use `references/interview-playbook.md` to guide discovery.

### Gate 1 — Adaptive end-to-end interview

Conduct an interview in phases, asking only high-value questions not already answered:

1. Problem, target users, current workaround, why now, and definition of success.
2. User types, permissions, primary and secondary tasks, critical end-to-end journeys.
3. Product scope, must-have features, exclusions, release sequence, monetization or business model if relevant.
4. UX preferences, brand/content tone, accessibility, devices/platforms/locales, competitor references if relevant.
5. Data, persistence, privacy, security, integrations, offline behavior, reliability, performance, regulatory or contractual constraints when applicable.
6. Technical constraints, existing stack/repo, hosting/distribution, budget, skills/team, deadline, operational ownership, maintenance expectations.
7. Risks, failure cases, acceptance criteria, launch/testing strategy, and open decisions.

Ask usually 3–7 questions in a turn, grouped by a clear theme. Prefer concrete choices with room for free-text nuance. Do not force answers that are genuinely unknown; record them as assumptions/questions with an owner and decision deadline. Explain trade-offs where a question could change architecture, cost, privacy, user workflow, or schedule. Avoid asking the user to decide low-level technical choices they have no reason to know; propose options and state consequences.

The interview is complete only when the readiness checklist in `references/interview-playbook.md` is satisfied or every remaining gap is explicitly logged. Summarize the product brief, constraints, scope, key journeys, success measures, major risks, and assumptions to the user. Ask for a concise confirmation/correction before treating high-impact assumptions as approved. If the user says to proceed without another confirmation, proceed and preserve the unapproved assumptions as such.

### Gate 2 — Canonical product brief and decisions

Create a single source of truth before specialist drafting. Recommended output root: `docs/product-blueprint/` for an existing repository, or `product-blueprint/` for a standalone planning package. Include:

- `00-product-brief.md`: problem, target users, outcomes, scope, constraints, terminology, known facts, assumptions, open questions.
- `00-decision-log.md`: `DEC-###`, context, options, decision, rationale, consequences, status, owner/date. Mark proposals separately from approved choices.
- `00-traceability-matrix.md`: user problems/outcomes → requirements → journeys/screens/entities → implementation milestones → verification criteria.

Do not duplicate changing decisions in six independent documents. Each document should link to the canonical decision log.

### Gate 3 — Launch specialist authoring roles

Use the orchestration rules in `references/agent-orchestration.md`. Assign a dedicated role to each required deliverable:

- **PRD specialist:** user and business value, scope, requirement IDs, acceptance criteria, non-functional requirements, analytics/success metrics, dependencies, release criteria.
- **TRD / system architecture specialist:** architecture, component boundaries, stack evaluation, interfaces, deployment/runtime, security/privacy, performance/reliability, observability, migration/rollback, technical decisions and alternatives.
- **Appflow / journey specialist:** personas/roles, entry/exit points, navigation hierarchy, happy paths, branches, edge cases, recoveries, Mermaid or equivalent flow diagrams, journey IDs and transition rules.
- **UI/UX specialist:** information architecture, screen inventory, layout hierarchy, interaction rules, design tokens, content voice, responsive behavior, accessibility, states, validation, error messages, and reusable components. Produce wireframes/specifications in the available format; do not claim visual assets exist unless created.
- **Backend / data-schema specialist:** identify whether a backend is actually needed. Model entities, fields, types, keys, relationships, constraints, indexes, lifecycle, ownership, authorization, retention, migrations, seed/test data, APIs/events, and transaction/idempotency needs where applicable. For local-first or static products, explicitly document the appropriate local data model or “no backend” rationale instead of forcing a server.
- **Implementation-plan specialist:** dependency graph, workstreams, milestones, thin vertical slices, task breakdown, owners/roles, risk, estimates with stated confidence, test strategy, exit criteria, release and rollback gates.
- **Independent product/reliability reviewer:** does not simply rewrite the drafts; finds contradictions, missing journeys, untestable requirements, unsupported technical assumptions, UX hazards, security/privacy gaps, schedule risks, and scope creep. This reviewer is a quality role, not an extra required product document.

Optional research, threat-model, accessibility, domain, and test strategy roles may be added when risk or product type warrants them. Do not spawn agents without a concrete assignment, context, expected output, and review criteria. Do not allow agents to modify source code while they are writing planning documents.

### Gate 4 — Assemble the six documents

Use the contracts and templates in `references/document-contracts.md` and `templates/`. Required output filenames:

1. `01-PRD.md`
2. `02-TRD.md`
3. `03-APPFLOW-USER-JOURNEYS.md`
4. `04-UI-UX-DESIGN-SPEC.md`
5. `05-BACKEND-DATA-SCHEMA.md`
6. `06-IMPLEMENTATION-PLAN.md`

Use Markdown by default for durable, diffable version control. Add diagrams using Mermaid where supported; keep text descriptions alongside diagrams so the document remains understandable if diagrams cannot render. Each document must have a status/version, scope, assumptions, references to relevant `DEC-###` and stable IDs, and a revision/change note.

### Gate 5 — Cross-document integration review

The reviewer must check at minimum:

- Every P0/P1 product requirement maps to one or more user journeys and acceptance criteria.
- Every journey step has a plausible screen/interface and success, empty, loading, error, and recovery behavior where relevant.
- UI forms/actions match the data schema and API contracts; field names, types, validation, permissions, and state transitions agree.
- The TRD fits the product's stated offline/online, privacy, platform, hosting, distribution, reliability, and budget constraints.
- The data model supports stated workflows without unnecessary entities or premature complexity.
- Implementation milestones follow dependencies and deliver thin, testable vertical slices, not giant frontend/backend phases that cannot be demonstrated end to end.
- Security, privacy, accessibility, localization, compatibility, monitoring, backups, migration, recovery, and support are included when applicable.
- Estimates expose uncertainty; no made-up precision. Out-of-scope features are not hidden in implementation tasks.
- No unsupported fact, inconsistent naming, duplicated conflicting rule, missing error path, or acceptance criterion that cannot be observed.

Create `07-CONSISTENCY-AND-OPEN-ISSUES.md` with issues, severity, affected docs/IDs, recommended fix, owner, and status. If a conflict changes product intent, ask the user; do not resolve it by guessing. For lower-impact conflicts, propose a reasoned default and label it pending approval. Re-run the affected author/reviewer passes until no critical contradictions remain.

### Gate 6 — Create the milestone-wise development operating plan

The implementation plan must turn the documents into controlled delivery work. Use `references/milestone-gated-engineering.md`. Define milestones appropriate to the project instead of blindly using the same number for every app. Each milestone needs:

- Outcome demonstrated to a user or operator.
- Included requirement/journey IDs and explicit exclusions.
- Dependency and prerequisite checks.
- Tasks, deliverables, responsible roles, and acceptance criteria.
- Unit/component, integration, end-to-end, accessibility, security, and manual checks as relevant.
- Demo/review gate and definition of done.
- Rollback/recovery strategy for risky changes.
- Risks, unresolved decisions, and entry/exit conditions.

At minimum consider: product foundation and developer workflow; one thin end-to-end core journey; remaining critical journeys; hardening and operational capabilities; release candidate and closed testing; launch and post-launch feedback. Merge or split based on project scale. Add a `manifest.md` or equivalent project memory file when useful, recording project intent, chosen stack and rationale, architecture map, current milestone, decisions, commands, known issues, and how an agent should resume without re-investigating everything. Do not write secrets into memory/docs.

If the user asks only for planning documents, create the plan and starter operating artifacts, but do not install packages, change app code, migrate databases, provision services, or deploy. If the user explicitly asks to set up the development environment too, first inspect the existing repository and propose/record the changes; use a branch when the repo workflow supports it; never run destructive or production-affecting actions without explicit authorization.

### Gate 7 — Delivery and handoff

Deliver links/paths for all six documents, product brief, decision log, traceability matrix, and consistency report. Summarize confirmed decisions, major trade-offs, assumptions, unresolved questions, biggest risks, and first milestone. State which agents ran in parallel versus sequentially and which verification activities actually occurred. Do not claim tests, research, diagrams, or files were created unless they were.

## Working with existing projects

When an existing repository or prior conversation is available:

- Read `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `manifest.md`, README, package manifests, architecture and design docs, and relevant source/tests. Follow repository instructions.
- Inspect current git status before writing. Preserve user changes. Never reset, clean, stash, force checkout, overwrite, delete, or reformat unrelated files as a side effect of planning.
- Treat working code and observed test output as evidence, but do not assume implementation matches written requirements. Record mismatches.
- Mark existing architecture as current-state and distinguish it from proposed target-state architecture.
- Avoid recreating plans already present; compare, update carefully, and provide a changelog. Never overwrite authoritative docs without explicit permission.

## Definition of done

The skill run is complete only when: the interview/readiness gaps are resolved or logged; the product brief and decision log exist; all six deliverables exist; every key requirement has traceability; the independent review has been performed; critical contradictions are fixed or explicitly blocked on a user decision; a milestone-wise implementation plan has exit criteria; files are readable and internally linked; and final output clearly distinguishes decisions, proposals, and unknowns.

## Reference material

Read these as needed; do not paste them all into every response:

- [Interview playbook](references/interview-playbook.md)
- [Specialist-agent orchestration](references/agent-orchestration.md)
- [Six-document contracts](references/document-contracts.md)
- [Milestone-gated engineering](references/milestone-gated-engineering.md)
- [Human-centered quality bar](references/human-centered-quality-bar.md)
- [Repository completion trigger](templates/AGENT_COMPLETION_TRIGGER.md)
