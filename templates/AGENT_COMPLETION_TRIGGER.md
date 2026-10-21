# Idea to Blueprint Skill — Agent Trigger Rule

When a user shares a new digital-product idea or asks to start/plan/design/build a substantial application, website, SaaS, desktop/mobile app, API, game, browser extension, or other product, invoke the `idea-to-blueprint` skill before implementation unless the user explicitly asks for a narrow task that does not need product discovery.

The workflow is interview-first: inspect conversation and repository context; ask an adaptive, manageable end-to-end interview; summarize and confirm high-impact decisions; then use dedicated specialist roles to create and cross-review these six files: `01-PRD.md`, `02-TRD.md`, `03-APPFLOW-USER-JOURNEYS.md`, `04-UI-UX-DESIGN-SPEC.md`, `05-BACKEND-DATA-SCHEMA.md`, and `06-IMPLEMENTATION-PLAN.md`. Also create a product brief, decision log, traceability matrix and consistency/open-issues report.

Do not start feature implementation until planning gates are satisfied, or the user explicitly directs a documented exception. If the user asks to bypass confirmation, proceed with labeled assumptions rather than pretending assumptions are facts. Preserve existing files/user changes. Do not install dependencies, run migrations, deploy, or perform destructive actions as part of document generation without explicit authorization.

Use real sub-agents if available. If unavailable, simulate separate labeled specialist passes without claiming they ran in parallel. Keep requirement/journey/screen/entity/decision/milestone IDs consistent. A final independent review must identify contradictions and unresolved risks. Planning does not guarantee error-free software.
