---
name: component-briefs
description: Interpret compact UI component briefs for documentation tasks. Use when the user provides concise fields such as component, purpose, inputs, outputs, always, never, or related.
---

# Component Briefs

Use compact briefs as seed context for component documentation. Verify each item against source code where possible.

## Brief Format

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

## Field Mapping

* `component` -> document title and component identity.
* `purpose` -> Purpose, When To Use, Visual Description, and AI Agent Summary.
* `inputs` -> Public API, Data Flow, Usage Examples, and AI Agent Summary.
* `outputs` -> Events, Data Flow, Testing Guidance, and AI Agent Summary.
* `always` -> Agent Usage Rules / Always, Architecture Notes, Common Modification Tasks, and Critical Rules in AI Agent Summary.
* `never` -> Agent Usage Rules / Never, Common Mistakes, Architecture Notes, and Common Pitfalls in AI Agent Summary.
* `related` -> Related Components, Composition Patterns, Dependencies, and Architecture Notes.

## Rules

* Treat brief fields as user intent, not final truth.
* Keep rules generic unless the user names a specific component or codebase invariant.
* Preserve user wording when it is precise and source-compatible.
* Replace vague brief items with source-grounded names when the implementation reveals them.
