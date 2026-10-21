# Human-Centered Product Quality Bar — Anti-Slop Review

## Product clarity
- Does the product solve a specific, evidenced user problem?
- Can a first-time user explain what to do next without reading a manual?
- Are core actions obvious and are destructive/irreversible actions clearly signaled?
- Are benefits stated honestly, without generic AI/product claims?
- Are features prioritized by value and constraint rather than quantity?

## Interaction quality
- Each screen has a clear primary task and meaningful hierarchy.
- Every interactive element has an observable outcome, not a decorative purpose.
- Loading/progress states explain what is happening and what users can do while waiting.
- Errors describe the problem in plain language and give a safe recovery action.
- Empty states teach the next useful step without fake data presented as real.
- Form validation is near the affected field, preserves user input where safe, and explains correction.
- Long operations support cancel/retry/recovery where appropriate; no false success messages.
- Navigation, keyboard, touch, responsive layouts and platform conventions match target users.

## Content quality
- Labels are short, concrete verbs/nouns used consistently.
- Avoid unexplained jargon for end users; use technical language only when the user needs it.
- No generic placeholder copy, repeated marketing adjectives, fake testimonials, invented statistics or fake logos.
- Empty/error/success content is written for the actual context.
- Onboarding appears only where users need it and can be skipped or revisited when appropriate.

## Design integrity
- Visual hierarchy supports task priority and reading order.
- Design tokens and components are consistent and justified by the brand/context.
- Color is not the only carrier of state; contrast and focus visibility are specified.
- Motion, gradients, glassmorphism, card grids, AI chat affordances and other trends are not added automatically.
- Reference products are studied for specific patterns and constraints, not copied blindly.

## Trust, privacy and control
- Users can understand what data is collected, where it goes, how it is saved and how to recover/export/delete it where applicable.
- Permission requests appear in context and explain why they are needed.
- AI behavior (if any) has clear boundaries, human control, failure handling, source/uncertainty communication when relevant, and no fabricated capability claims.
- There is a clear path to undo, cancel, revise or correct mistakes for significant user actions where technically possible.

## Review output
For each finding include severity (`Critical`, `High`, `Medium`, `Low`), affected IDs/section, user impact, evidence or rationale, and concrete recommended correction. Do not call the work “humanized” only because it uses friendly wording; judge it by task clarity, user control, relevance and recoverability.
