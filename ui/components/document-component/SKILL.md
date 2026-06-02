---
name: document-component
description: Generate complete AI-agent-friendly UI component documentation. Use for end-to-end component documentation tasks that require reading implementation, tests, stories, and usage, then assembling a structured documentation file.
---

# Document Component

Create a complete documentation file for a UI component that is useful to human developers and coding agents.

## Workflow

1. Locate the component source file and identify the exported component name.
2. Inspect related hooks, types, constants, utilities, styles, tests, Storybook stories, and nearby export files.
3. Search the codebase for real usages and note common patterns.
4. Read supporting smaller skills as needed:
   * `../component-briefs/SKILL.md`
   * `../component-api/SKILL.md`
   * `../component-usage/SKILL.md`
   * `../component-maintenance/SKILL.md`
   * `../component-agent-profile/SKILL.md`
5. Write the final documentation in the exact section order below.
6. Use realistic examples from the codebase whenever possible.
7. If a section has no source evidence, state what is unknown instead of inventing facts.
8. If the user asks for an agent-specific YAML file, create it using `../component-agent-profile/SKILL.md` alongside the human-readable documentation.

## Required Section Order

Use this exact top-level structure:

```markdown
# Component Name

## Purpose

## When To Use

## When NOT To Use

## Visual Description

## Dependencies

## Public API

## Internal State

## Data Flow

## Events

## Accessibility

## Usage Examples

### Minimal Example

### Typical Example

### Advanced Example

### Real Project Example

## Agent Usage Rules

### Always

### Never

### Common Mistakes

## Composition Patterns

## Styling Rules

## Performance Considerations

## Testing Guidance

## Common Modification Tasks

## Related Components

## Architecture Notes

## AI Agent Summary
```

## Final Pass

Before finishing:

* Confirm every prop, event, state value, and dependency is grounded in source or clearly marked as inferred.
* Confirm examples compile conceptually with the component API.
* Confirm agent rules are actionable and specific.
* Confirm the AI Agent Summary can be understood in under 30 seconds.
