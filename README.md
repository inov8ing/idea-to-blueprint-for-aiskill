<div align="center">

# ?? idea-to-blueprint

### Turn raw ideas into implementation-ready product blueprints

**An AI agent skill that conducts adaptive product interviews and generates six professionally structured planning documents — fully traceable, cross-reviewed, and milestone-gated.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Agent Skill](https://img.shields.io/badge/Type-Agent%20Skill-purple.svg)]()

---

*"Don't build the wrong thing. Blueprint it first."*

</div>

## ?? What It Does

**idea-to-blueprint** is a reusable agent skill that transforms a rough product idea, user request, or existing codebase into a **complete, implementation-ready product blueprint** through:

1. ??? **Adaptive Interview** — Context-aware, conversational product discovery (not a questionnaire dump)
2. ?? **Specialist Agents** — Dedicated roles for PRD, architecture, UX, data, and planning
3. ?? **Cross-Document Review** — Independent consistency checks with traceability
4. ?? **Milestone-Gated Engineering** — Thin vertical slices with demo gates and rollback paths

## ?? Generated Documents

| # | Document | What It Covers |
|---|----------|---------------|
| 1 | `01-PRD.md` | Requirements, acceptance criteria, success metrics, scope |
| 2 | `02-TRD.md` | Architecture, stack rationale, deployment, security, reliability |
| 3 | `03-APPFLOW-USER-JOURNEYS.md` | Personas, end-to-end journeys, flows, error recovery |
| 4 | `04-UI-UX-DESIGN-SPEC.md` | Screen inventory, interactions, design tokens, accessibility |
| 5 | `05-BACKEND-DATA-SCHEMA.md` | Entities, APIs, data lifecycle, authorization, migrations |
| 6 | `06-IMPLEMENTATION-PLAN.md` | Milestones, tasks, dependencies, estimates, release gates |

**Plus control artifacts:** Product Brief, Decision Log, Traceability Matrix, and Consistency Report.

## ??? How It Works

`
+----------------------------------------------------------+
¦                    idea-to-blueprint                     ¦
+----------------------------------------------------------¦
¦                                                          ¦
¦  Gate 0  ?  Intake & Context Inspection                  ¦
¦  Gate 1  ?  Adaptive End-to-End Interview                ¦
¦  Gate 2  ?  Canonical Product Brief & Decisions          ¦
¦  Gate 3  ?  Specialist Agent Authoring (6 roles)         ¦
¦  Gate 4  ?  Document Assembly                            ¦
¦  Gate 5  ?  Cross-Document Integration Review            ¦
¦  Gate 6  ?  Milestone-Gated Development Plan             ¦
¦  Gate 7  ?  Delivery & Handoff                           ¦
¦                                                          ¦
+----------------------------------------------------------+
`

## ? Quick Start

### 1. Install

Copy the `idea-to-blueprint` skill directory into the skill discovery folder used by your coding agent:

`ash
# Example for agents using ~/.gemini/config/skills/
cp -r idea-to-blueprint ~/.gemini/config/skills/idea-to-blueprint
`

> **Note:** Installation paths vary by agent tool. Follow your agent's skill documentation.

### 2. Use

Simply describe your product idea to your agent. The skill activates automatically when you:

- Share a **new product idea**
- Ask to **plan, design, or architect** a product
- Ask for a **PRD, TRD, or technical blueprint**
- Request planning for an **existing codebase**

`
"I want to build a collaborative whiteboard app for remote teams 
with real-time sync, export to PDF, and offline support."
`

The agent will inspect context, interview you in manageable batches, and produce the full blueprint.

## ?? Repository Structure

`
idea-to-blueprint/
+-- SKILL.md                          # Core skill instructions (entry point)
+-- README.md                         # This file
+-- LICENSE                           # MIT License
+-- CONTRIBUTING.md                   # Contribution guidelines
+-- agents/
¦   +-- README.md                     # Agent role definitions
+-- references/
¦   +-- interview-playbook.md         # Interview phases & completion checklist
¦   +-- agent-orchestration.md        # Specialist role assignments & scheduling
¦   +-- document-contracts.md         # Six-document quality contracts
¦   +-- milestone-gated-engineering.md # Delivery milestone playbook
¦   +-- human-centered-quality-bar.md # Anti-slop UX quality review
+-- templates/
    +-- AGENT_COMPLETION_TRIGGER.md   # Repository-level agent rule
    +-- PRD.template.md
    +-- TRD.template.md
    +-- APPFLOW-USER-JOURNEYS.template.md
    +-- UI-UX-DESIGN-SPEC.template.md
    +-- BACKEND-DATA-SCHEMA.template.md
    +-- DECISION-LOG.template.md
    +-- IMPLEMENTATION-PLAN.template.md
`

## ??? Safety Model

| Principle | Detail |
|-----------|--------|
| **Read-only by default** | Planning never modifies source code unless explicitly authorized |
| **No invented certainty** | Assumptions are labeled, not hidden as facts |
| **Preserve existing work** | Never overwrites files, resets git, or discards uncommitted changes |
| **No secrets in docs** | Credentials and sensitive config stay out of generated artifacts |
| **Honest verification** | Never claims tests, research, or agents ran unless they actually did |

## ?? Compatibility

This skill is **agent-agnostic** and works with any AI coding assistant that supports the skill/instruction file pattern:

- **Google Antigravity / Gemini** — Place in `~/.gemini/config/skills/`
- **Cursor** — Place in `.cursor/skills/` or equivalent
- **Claude Code / Codex** — Use `AGENTS.md` trigger template (included)
- **Other agents** — Follow your agent's skill loading docs

## ?? Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## ?? License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Built with ?? by [@inov8ing](https://github.com/inov8ing)**

*Stop guessing. Start blueprinting.*

</div>