# Milestone-Gated Engineering Playbook

## Principle

Plan delivery around user-observable vertical outcomes, not only technical layers. A milestone is a bounded change that can be reviewed, tested and demonstrated. Each gate should make uncertainty smaller before the next expensive commitment.

## Common milestone families

Adapt count and order to the project; these are options, not a mandatory waterfall:

### MS-00 — Product and repository baseline
- Confirm product brief, requirements baseline, architecture decisions and risk register.
- Record current repository state, runtime/toolchain versions, setup instructions, environment variables by name only (never values), scripts, and test commands.
- Establish version control, branch/PR conventions, formatting/linting/type checking, minimal CI, test strategy, and secret-handling rules.
- Exit: a fresh developer can reproduce setup; baseline checks and known failures are documented; no user changes were discarded.

### MS-01 — Architecture proof / riskiest assumption
- Spike only the high-risk, expensive, novel or platform-dependent questions identified in the TRD.
- Test actual tool/API/library constraints, data volume, offline/online behavior, media/device integration or performance assumptions as applicable.
- Exit: evidence, benchmark/test reproduction steps, chosen option, rejected alternatives and updated ADR. If the risk fails, revise architecture before building around it.

### MS-02 — First thin vertical slice
- Complete one valuable journey end to end: entry → action → validation → persistence or processing → visible outcome → error handling → test.
- Use production-like boundaries and real integration contracts; avoid fake UI connected only to mock behavior unless clearly a time-boxed prototype.
- Exit: accepted journey, integration and appropriate end-to-end tests pass; error and recovery behavior is demonstrated.

### MS-03 — Remaining critical journeys
- Deliver prioritized journeys in small, dependency-aware increments.
- Include authorization, data integrity, state persistence, empty/error/loading states and tests with each slice.
- Exit: P0 journeys and requirement traceability are satisfied or gaps have approved risk disposition.

### MS-04 — Product quality and operations hardening
- Address accessibility, compatibility, performance, security/privacy review, logging/telemetry, crash/error reporting, backups/recovery, migrations and dependency failure as appropriate.
- Exit: measurable targets are tested under documented conditions; critical defects are resolved; operational owners and playbooks exist.

### MS-05 — Release candidate and closed testing
- Package/version a reproducible candidate. Prepare human closed-testing checklist, test accounts/data, release notes, support path, known issues, rollback and feedback loop.
- Triage defects by severity and frequency; distinguish code fixes from unclear requirements and usability issues.
- Exit: release criteria are met or exceptions have named approvers and documented rationale. Do not disguise an untested critical flow with an overall percentage.

### MS-06 — Launch and learn
- Controlled deployment/distribution, smoke checks, monitoring, support readiness and rollback threshold.
- Review feedback and outcomes against success metrics. Prioritize follow-ups based on evidence.
- Exit: release health reviewed, incidents/feedback triaged, and next decision recorded.

## Gate template

For each milestone record:
- ID/name and intended user/business outcome.
- Entry criteria and dependencies.
- In-scope requirements/journeys and explicit exclusions.
- Tasks and expected artifacts.
- Owner role and reviewer/approver.
- Test layers and evidence required.
- Acceptance/exit criteria observable by another person.
- Risk/uncertainty and rollback/recovery path.
- Status (`Not started`, `In progress`, `Blocked`, `Ready for review`, `Accepted`) and decision date.

## Engineering workflow controls

- Use Git, small focused changes, reviewable commits, branch/PR workflow, and protected main branch where the project's scale/tooling supports it.
- Run relevant checks early and in CI, not only at release. Keep failing baseline checks visible instead of attributing them to new changes.
- Include tests with the feature. Test the behavior at the cheapest reliable level, then add integration and end-to-end coverage for important contracts and journeys.
- Use feature flags or staged rollout only when they reduce real risk and operational complexity is acceptable.
- Use migration plans and backwards compatibility checks for persisted data and public interfaces.
- Keep environment-specific configuration outside source control; document required variables by name and purpose without secret values.
- Maintain `manifest.md` or equivalent with current milestone, verified setup and commands, architecture map, important decisions, open issues, last verification results, and precise next task.
- Capture changes in scope or architecture in the decision log and revise affected documents/traceability before implementation drifts.

## Definition of done for each increment

Code review complete; acceptance criteria met; appropriate automated checks pass; error/loading/empty/recovery paths addressed; accessibility/compatibility impact considered; documentation and observability updated as needed; security/privacy implications considered; migrations reversible or recovery understood; no known critical regressions; demo/evidence captured; milestone status updated.
