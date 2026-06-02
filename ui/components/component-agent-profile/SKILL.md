---
name: component-agent-profile
description: Create machine-readable YAML profiles for UI components so coding agents can quickly understand component purpose, inputs, outputs, rules, risks, dependencies, accessibility, performance, related components, and safe extension points.
---

# Component Agent Profile

Create a YAML file specifically for coding agents. Use it alongside the human-readable component documentation when the user asks for an agent file, YAML file, machine-readable profile, compact component profile, or agent-specific component guidance.

## File Purpose

The YAML profile should let a coding agent understand the component's contract in under 30 seconds.

Use it for:

* Critical rules and invariants
* Fast component selection
* Safe modification guidance
* Cross-agent handoff
* Preventing common implementation mistakes

## File Naming

Prefer one of these names, depending on the project convention:

* `<ComponentName>.agent.yaml`
* `<ComponentName>.component.yaml`
* `agent.yaml` inside a component documentation folder

Keep the filename stable once introduced.

## YAML Shape

Use this structure:

```yaml
component: ComponentName

category: category-name

purpose: >
  Concise explanation of what the component does.

inputs:
  - primaryInput
  - configurationInput
  - stateInput

outputs:
  - userInteractionOutput
  - callbackOutput
  - stateChangeOutput

dependencies:
  - RequiredContext
  - requiredHook
  - externalLibrary

always:
  - preserve required invariants
  - use provided contexts, stores, and hooks

never:
  - mutate props or input data
  - fetch data directly unless the component is explicitly responsible for fetching

accessibility:
  - keyboard behavior requirement
  - screen reader or ARIA requirement

performance:
  - memoization requirement
  - virtualization or lazy-loading requirement

common_mistakes:
  - common mistake agents should avoid
  - another recurring misuse

related_components:
  - ParentComponent
  - ChildComponent
  - AlternativeComponent

extension_points:
  - supported customization point
  - safe integration point

agent_summary:
  critical_rules:
    - highest-priority invariant
    - highest-priority state rule

  safe_modifications:
    - safe extension task
    - safe UI enhancement

  risky_modifications:
    - risky architectural change
    - risky state-management change
```

## Field Guidance

* `component` - Use the exported component name.
* `category` - Use a concise domain label such as `data`, `navigation`, `layout`, `form`, `feedback`, `timeline`, `media`, or `editor`.
* `purpose` - Summarize the component responsibility, not every implementation detail.
* `inputs` - Include props, externally controlled state, context inputs, and important configuration.
* `outputs` - Include callbacks, emitted events, selection changes, state updates, navigation effects, or rendered output contracts.
* `dependencies` - Include only dependencies that affect correct usage or safe modification.
* `always` - Include non-negotiable usage and modification rules.
* `never` - Include rules that prevent bugs, architectural drift, or state corruption.
* `accessibility` - Include required keyboard, ARIA, focus, and screen reader behavior.
* `performance` - Include memoization, virtualization, stable identity, lazy loading, and expensive-render constraints.
* `common_mistakes` - Include mistakes visible in source, tests, bug history, or likely agent misuse.
* `related_components` - Include parent, child, similar, replacement, or companion components.
* `extension_points` - Include safe ways to extend behavior without rewriting internals.
* `agent_summary` - Include only the most important rules, safe changes, and risky changes.

## Rules

* Keep YAML valid and machine-readable.
* Use arrays for repeatable fields even when there is only one item.
* Prefer concrete component-specific names over generic wording after source analysis.
* Do not include Markdown headings inside YAML values.
* Do not duplicate the full human-readable documentation.
* Do not invent dependencies, rules, or extension points not supported by the source or user-provided brief.
* Mark uncertain values as `unknown` only when source analysis cannot resolve them.
