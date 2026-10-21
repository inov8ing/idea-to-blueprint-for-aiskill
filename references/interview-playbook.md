# End-to-End Product Interview Playbook

## Principles

Interview for decisions, not for the sake of asking questions. Ask the smallest set of questions that changes product scope, user flows, architecture, risk, cost, or schedule. Read available context first and never ask the user to repeat known answers. One turn should usually contain 3–7 related questions. Give plain-language examples and explain why an answer matters when the choice is consequential.

Do not require the user to know engineering jargon. Offer options such as “local-only / sync through account / not sure” instead of asking for a database or protocol. “Not sure yet” is a valid answer; track it as an assumption or decision to resolve.

## Phase 0 — Intake

Determine:
- Is this a new concept, feature, redesign, migration, or an existing codebase?
- What did the user supply: rough idea, voice note/transcript, screenshots, competitor links, spec, source code, or partial decisions?
- What output and depth do they want? Default to all six docs and the control artifacts defined in the main skill.
- Is there an existing source of truth such as `manifest.md`, an issue tracker, designs, or README?

Start with a brief neutral restatement of the current understanding and ask only the most useful missing questions.

## Phase 1 — Problem and value

Discover:
- Who has the problem and in what real-world context?
- What are they trying to accomplish? What do they do today and what is painful about it?
- Why would they switch to this product? What makes the solution meaningfully different?
- What should change for the user after using it?
- How will the owner measure success after launch? Include baseline/target/time window when known.

Do not accept a feature list as a substitute for a problem statement. Map each major feature back to a user need or a justified platform requirement.

## Phase 2 — Users and journeys

Discover primary personas, skill levels, accessibility needs where relevant, permission/role differences, acquisition/entry point, first-use experience, core task, completion signal, repeat use, collaboration, sharing/export, support and failure recovery.

Ask the user to describe their most important task in everyday language. Convert it into start → actions/decisions → system response → verified outcome. Look for alternate paths, interruptions, cancellation, retries, and “what if this fails?” states.

## Phase 3 — Scope and priority

Separate:
- P0 / must exist for the first usable release.
- P1 / important soon, but can follow if explicitly accepted.
- P2 / enhancement.
- Out of scope / explicitly excluded.

Ask what must not be included. Distinguish first public release from later roadmap. Do not use “MVP” to excuse missing critical reliability or safety behavior. If the user wants full production quality, plan production readiness rather than pretending all features can fit a short first milestone.

## Phase 4 — Product and design character

Discover brand personality, tone of voice, content principles, design references, dislikes, density, visual style, platform conventions, responsive targets, input modalities, language/locale, accessibility needs, and any existing design system. Ask about preferences through examples, but do not assume a reference should be copied wholesale.

Human-centered prompts:
- What should a first-time user understand in the first minute?
- What is the most common task, and how many decisions should the interface ask the user to make?
- Where might the user be confused, anxious, interrupted, or afraid of losing work?
- What should error messages explain and what recovery action should be offered?
- What must remain visible while a long-running operation is in progress?

## Phase 5 — Data, integration, and constraints

Based on product type, ask about account requirements, data sensitivity, ownership, collaboration, retention/deletion/export, offline behavior, sync conflicts, external services, rate limits/cost, uploads, payments (sandbox first), notifications, import/export, backup/recovery, and audit needs.

Discover target platforms and distribution, expected scale (rough order of magnitude is enough), performance-critical actions, uptime expectations, hosting or local-only requirements, delivery deadline, available skills/team, budget, maintenance, update channel, support and monitoring.

Do not demand compliance answers from a non-expert. Ask about geography, user population, data types, business context, and contractual obligations; flag potential legal/security review rather than asserting a specific compliance conclusion without evidence.

## Phase 6 — Acceptance and risks

For each core requirement, ask what a tester should observe to determine it works. Examples: “exported file opens in the supported player with audio in sync” is better than “export works.”

Capture:
- Positive outcome and key negative/error cases.
- Data loss, privacy, payment, account, and permission risks.
- Most expensive technical unknowns.
- External dependency and vendor risks.
- Migration, recovery, rollback, and support expectations.
- How closed testing and release approval will work.

## Interview completion checklist

Before document authoring, ensure the following are either answered or explicitly recorded as unknown/assumption:

- [ ] Problem and intended outcome.
- [ ] Primary users and highest-value job.
- [ ] Core end-to-end journeys.
- [ ] First-release scope and explicit exclusions.
- [ ] Platforms, distribution, and key constraints.
- [ ] Success metrics or an agreed way to evaluate value.
- [ ] Critical data, privacy, permission, and persistence expectations.
- [ ] Required integrations and failure behavior.
- [ ] UX direction and accessibility/responsive needs where relevant.
- [ ] Quality attributes (performance, reliability, security, compatibility) relevant to the product.
- [ ] Acceptance criteria for P0 flows.
- [ ] Major risks and irreversible choices.
- [ ] Remaining unknowns have owner, impact, and a resolution milestone.

If the user is unable to answer all questions, do not stall indefinitely. Propose safe defaults, list trade-offs, mark approval status, and keep the relevant milestone blocked where the unknown has high impact.

## Interview synthesis message

Summarize:
1. Product in one paragraph.
2. Target users and most important problem.
3. Core release outcomes and top journeys.
4. Proposed scope and exclusions.
5. Major technical/operational constraints.
6. Proposed decisions and their rationale.
7. Assumptions/open questions and risk.

Invite corrections and confirmation of high-impact assumptions. If the user directs you to proceed, author while preserving the distinction between confirmed and assumed.
