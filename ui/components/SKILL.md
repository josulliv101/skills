---
name: components
description: Coordinate smaller UI component documentation skills. Use when asked to create AI-agent-friendly documentation for a UI component by analyzing source, hooks, types, tests, Storybook stories, and usage throughout a codebase.
---

# UI Component Documentation Skill Set

Use this skill as the entry point for documenting UI components for both humans and coding agents.

## Goal

Create documentation that lets another developer or AI agent correctly use, modify, extend, and troubleshoot a component without rereading the source code.

## Use The Smaller Skills

Load only the smaller skill files needed for the task:

* `document-component/SKILL.md` - End-to-end workflow and final document assembly.
* `component-briefs/SKILL.md` - Compact component brief format and field mapping.
* `component-api/SKILL.md` - Props, dependencies, internal state, data flow, and events.
* `component-usage/SKILL.md` - Purpose, use cases, visual behavior, accessibility, examples, composition, and styling.
* `component-maintenance/SKILL.md` - Agent rules, performance, tests, modification tasks, related components, architecture notes, and AI summary.

## Default Flow

1. Start with `document-component/SKILL.md`.
2. If the user provides a compact brief, also load `component-briefs/SKILL.md`.
3. Load `component-api/SKILL.md`, `component-usage/SKILL.md`, and `component-maintenance/SKILL.md` as needed to fill the required sections.
4. Verify facts against source code where possible.
5. Assemble the final documentation in the section order defined by `document-component/SKILL.md`.

## Ground Rules

* Prefer facts from source over assumptions.
* Say when information is unknown or not discoverable.
* Use real project examples when available.
* Label generated examples clearly when no real usage exists.
* Preserve explicit user-provided rules unless source code disproves them.
