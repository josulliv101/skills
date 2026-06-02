---
name: component-maintenance
description: Document UI component maintenance guidance for coding agents, including usage rules, performance, tests, safe modification tasks, related components, architecture notes, and concise AI summaries.
---

# Component Maintenance Documentation

Use this skill to document how agents and developers should safely modify and troubleshoot a component.

## Agent Usage Rules

Create explicit instructions for coding agents.

### Always

List things agents should always do. Include required hooks, contexts, IDs, controlled-mode patterns, ordering invariants, and accessibility requirements.

### Never

List things agents should never do. Include mutation, bypassing shared state, breaking context contracts, ignoring callback semantics, and styling outside the design system.

### Common Mistakes

List mistakes frequently made by developers or agents. Prefer mistakes visible in code comments, tests, bug fixes, or recurring usage patterns.

## Performance Considerations

Document:

* Expensive renders
* Memoization
* Virtualization
* Lazy loading
* Re-render triggers

Explain what agents should avoid and which props or state changes are performance-sensitive.

## Testing Guidance

Document:

* Critical behaviors
* Expected interactions
* Edge cases
* Existing test coverage
* Missing test coverage

Recommend focused tests for new behavior and regression-prone paths.

## Common Modification Tasks

Explain how to safely:

* Add new props
* Add new UI states
* Add new actions
* Extend functionality
* Refactor internals

Provide step-by-step guidance and note files that usually need updates.

## Related Components

List:

* Similar components
* Parent components
* Child components
* Replacements
* Alternatives

Explain relationships and when to choose each alternative.

## Architecture Notes

Explain implementation details future agents must understand before making changes:

* Invariants
* Assumptions
* Constraints
* Technical debt
* Historical decisions if discoverable

## AI Agent Summary

End with a concise section for coding agents:

```text
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
```

This section should allow an AI agent to understand the component in under 30 seconds.
