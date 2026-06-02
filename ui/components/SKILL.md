---
name: components
description: Generate AI-agent-friendly documentation for UI components. Use when asked to document a component by analyzing its implementation, related hooks, types, tests, Storybook stories, and codebase usage so future developers or coding agents can use, modify, extend, and troubleshoot the component without rereading the source.
---

# Generate AI-Agent-Friendly Component Documentation

Analyze the component implementation, related hooks, types, tests, Storybook stories, and usage throughout the codebase.

Create a documentation file for the component optimized for both human developers and coding agents such as Claude Code, Cursor, Codex, Gemini CLI, OpenAI Agents, and similar tools.

The goal is that another AI agent should be able to correctly use, modify, extend, and troubleshoot the component without needing to study the source code.

## Workflow

1. Locate the component source file and read the implementation.
2. Inspect related hooks, types, constants, utilities, styles, tests, Storybook stories, and nearby index/export files.
3. Search the codebase for real usages of the component and record common patterns.
4. Prefer facts from source over assumptions. When something is unknown, say so clearly.
5. Write the documentation using the exact structure below.
6. Use realistic examples from the codebase when available. If no real usage exists, provide plausible examples and label them as generated examples.
7. Include explicit coding-agent rules that prevent common misuse.

## Compact Component Briefs

When the user provides a compact component brief, use it as seed context and verify it against the source code where possible.

Map brief fields into the generated documentation as follows:

* `component` -> document title and component identity.
* `purpose` -> Purpose, When To Use, Visual Description, and AI Agent Summary.
* `inputs` -> Public API, Data Flow, Usage Examples, and AI Agent Summary.
* `outputs` -> Events, Data Flow, Testing Guidance, and AI Agent Summary.
* `always` -> Agent Usage Rules / Always, Architecture Notes, Common Modification Tasks, and Critical Rules in AI Agent Summary.
* `never` -> Agent Usage Rules / Never, Common Mistakes, Architecture Notes, and Common Pitfalls in AI Agent Summary.
* `related` -> Related Components, Composition Patterns, Dependencies, and Architecture Notes.

Example brief format:

```yaml
component: ComponentName

purpose: Concise description of the component responsibility

inputs:
  - primaryData
  - configuration
  - displayMode

outputs:
  - user interaction events
  - callback results

always:
  - preserve required context usage
  - maintain documented ordering or state invariants

never:
  - mutate props or input arrays
  - bypass shared state, context, or provided hooks

related:
  - ParentComponent
  - ChildComponent
  - SimilarComponent
```

## Required Documentation Structure

Use the following structure for the generated component documentation.

```markdown
# Component Name

## Purpose

Provide a concise explanation of what the component does.

Include:

* Primary responsibility
* Business purpose
* User-facing purpose
* Why the component exists

---

## When To Use

Describe scenarios where this component should be used.

Include:

* Common use cases
* Typical workflows
* Screens/pages where it belongs

---

## When NOT To Use

Describe situations where another component should be used instead.

Include:

* Anti-patterns
* Common mistakes
* Alternative components

---

## Visual Description

Describe what the component looks like and how it behaves.

Include:

* Layout
* Appearance
* States
* Responsive behavior
* Animations
* Interactions

Do not assume screenshots are available.

---

## Dependencies

List all important dependencies.

Include:

* Child components
* Shared UI primitives
* Hooks
* Context providers
* External libraries
* State management dependencies

---

## Public API

Document all props.

For each prop include:

* Name
* Type
* Required/Optional
* Default value
* Description
* Usage guidance

Use this table:

| Prop | Type | Required | Default | Description |
| ---- | ---- | -------- | ------- | ----------- |

---

## Internal State

Describe internal state management.

Include:

* useState
* reducers
* context
* derived state
* memoized values

Explain why each state exists.

---

## Data Flow

Describe:

Inputs ->
Transformations ->
State ->
Rendering ->
Outputs

Explain how data moves through the component.

---

## Events

Document all events.

Include:

* User interactions
* Callback props
* Keyboard interactions
* Mouse interactions
* Touch interactions

For each event describe:

* Trigger
* Effect
* Side effects

---

## Accessibility

Document:

* Keyboard support
* ARIA attributes
* Screen reader behavior
* Focus management
* Accessibility concerns
* Accessibility requirements

---

## Usage Examples

Provide:

### Minimal Example

### Typical Example

### Advanced Example

### Real Project Example

Use realistic examples from the codebase whenever possible.

---

## Agent Usage Rules

Create explicit instructions for coding agents.

Include:

### Always

List things agents should always do.

### Never

List things agents should never do.

### Common Mistakes

List mistakes frequently made by developers or agents.

---

## Composition Patterns

Describe:

* Parent components
* Child components
* Recommended combinations
* Common layouts

Explain how this component fits into larger workflows.

---

## Styling Rules

Document:

* CSS classes
* Tailwind conventions
* Theme integration
* Design tokens
* Layout constraints

Include styling restrictions agents must follow.

---

## Performance Considerations

Document:

* Expensive renders
* Memoization
* Virtualization
* Lazy loading
* Re-render triggers

Explain what agents should avoid.

---

## Testing Guidance

Document:

* Critical behaviors
* Expected interactions
* Edge cases
* Existing test coverage
* Missing test coverage

Provide recommended tests.

---

## Common Modification Tasks

Explain how to safely:

* Add new props
* Add new UI states
* Add new actions
* Extend functionality
* Refactor internals

Provide step-by-step guidance.

---

## Related Components

List:

* Similar components
* Parent components
* Child components
* Replacements
* Alternatives

Explain relationships.

---

## Architecture Notes

Explain important implementation details that future agents must understand before making changes.

Include:

* Invariants
* Assumptions
* Constraints
* Technical debt
* Historical decisions if discoverable

---

## AI Agent Summary

Provide a concise section specifically for coding agents.

Include:

Purpose:
...

Inputs:
...

Outputs:
...

Dependencies:
...

Critical Rules:
...

Common Pitfalls:
...

Safe Modifications:
...

This section should allow an AI agent to understand the component in under 30 seconds.
```
