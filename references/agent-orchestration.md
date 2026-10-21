# Specialist-Agent Orchestration

## Goal

Use independent specialist judgment without creating six disconnected documents. One orchestrator owns the canonical context, work assignment, ID registry, dependencies, and final merge. Specialist outputs are drafts until reviewed.

## Agent context packet

Give every sub-agent the same minimal context packet:
- Approved/current product brief and decision log.
- Interview transcript or summarized user answers, including constraints and dislikes.
- Confirmed facts vs assumptions vs proposals vs unresolved questions.
- Existing repo architecture and protected constraints, if applicable.
- Relevant requirements/journey/feature ID registry.
- Output filename, deliverable contract, known dependencies, and definition of done.
- Instruction to flag conflicts rather than silently resolve product choices.

Do not provide every source file to every agent indiscriminately. Supply relevant files and require explicit references for repository-grounded statements. Be mindful of private user data and credential exposure.

## Assignment model

### Orchestrator / Product Discovery Lead
Owns interview, canonical brief, decision log, priority definitions, stable ID registry, scope boundaries, document assembly and final delivery. Does not allow agents to invent or approve product decisions.

### Research and Evidence Analyst (conditional)
Researches current, niche, or high-risk claims, compares viable options against user constraints, and returns sourced findings with trade-offs and uncertainty. Does not decide the product without the owner.

### PRD Author
Owns product requirements and measurable acceptance criteria; cites journeys but does not invent architecture.

### System Architect / TRD Author
Owns architecture, stack evaluation, interfaces, runtime/deployment and technical quality attributes; consumes PRD and constraints. Must compare plausible options for consequential decisions and note rejected alternatives.

### Appflow / Journey Author
Owns journey diagrams, decision points, navigation and recovery routes; uses requirement IDs from the canonical registry.

### UI/UX Author
Owns screen inventory, information architecture, interaction patterns, UI states, content behavior and accessibility/responsive requirements; consumes journeys and brand/user research.

### Data Architect / Backend Schema Author
Owns entities, fields, relationships, API/event contracts, data lifecycle, authorization and migration needs. Must first determine whether a server backend is warranted.

### Implementation Planner
Owns dependency-ordered milestones, thin vertical slices, task groupings, verification gates, estimates and release plan. Does not re-prioritize requirements without recording the change.

### Independent Blueprint Reviewer
Receives the canonical brief and all six drafts. Looks for contradictions and blind spots, not style alone. Must output concrete findings tied to file sections and stable IDs, plus severity and recommended correction.

## Scheduling

Parallelize only independent first drafts after the brief, decisions, and IDs are stable. A useful first parallel wave is PRD, Appflow, and research. TRD depends on product outcomes and constraints; UI/UX depends on journeys and product tone; schema depends on requirements and architecture decisions; implementation plan depends on all other drafts. These dependencies can overlap when stable interfaces have been agreed, but mark provisional assumptions clearly.

Recommended process:
1. Orchestrator freezes brief v1 and ID registry.
2. Specialists create draft versions with assumptions stated.
3. Orchestrator shares relevant drafts across specialists for conflict resolution.
4. Each specialist updates only their own document and logs material changes.
5. Independent reviewer produces findings.
6. Orchestrator resolves findings with responsible authors and routes product-level conflicts to user.
7. Generate traceability matrix and consistency report, then re-review changed areas.

## Tool capability fallback

If the runtime supports sub-agent spawning, actually invoke them and capture their outputs. If not, run isolated role passes sequentially with each role's contract as a distinct heading/prompt. State honestly in the final delivery which mode was used. Never imply that concurrency, code execution, research, or review occurred when it did not.

## Avoid agent failure modes

- Do not ask all agents to “design the best app”; use narrow assignments with explicit outputs.
- Do not let agents rename stable requirement/entity/screen IDs independently.
- Do not have every agent select a different stack or repeat generic recommendations.
- Do not average contradictory recommendations. Surface the decision and trade-offs to the user.
- Do not accept a reviewer that only praises the work. Require findings and evidence, including “none found” with the checks performed.
- Do not generate more agents than the work justifies. A small brochure site may use combined sub-roles, while a data-heavy high-risk application deserves more separation.
