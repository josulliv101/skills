---
name: component-api
description: Document the technical API surface of UI components, including dependencies, props, internal state, data flow, and events.
---

# Component API Documentation

Use this skill to document the component's technical contract.

## Dependencies

List important dependencies:

* Child components
* Shared UI primitives
* Hooks
* Context providers
* External libraries
* State management dependencies

Explain how each dependency affects usage or modification.

## Public API

Document all props with this table:

| Prop | Type | Required | Default | Description |
| ---- | ---- | -------- | ------- | ----------- |

For each prop include:

* Name
* Type
* Required or optional status
* Default value
* Description
* Usage guidance

Mention controlled versus uncontrolled behavior, callback expectations, object identity concerns, and required IDs when relevant.

## Internal State

Describe internal state management:

* `useState`
* Reducers
* Context
* Derived state
* Memoized values

Explain why each state value exists and what updates it.

## Data Flow

Describe data movement as:

Inputs ->
Transformations ->
State ->
Rendering ->
Outputs

Include validation, sorting, filtering, memoization, formatting, and event emission where relevant.

## Events

Document all events:

* User interactions
* Callback props
* Keyboard interactions
* Mouse interactions
* Touch interactions

For each event describe:

* Trigger
* Effect
* Side effects

Include event ordering and cancellation behavior when discoverable.
