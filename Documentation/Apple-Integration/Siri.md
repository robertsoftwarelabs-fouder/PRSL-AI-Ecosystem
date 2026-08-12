# PRSL-AI Siri Architecture

## Purpose

Siri is treated as an Apple interaction surface through which humans can invoke selected @iRiel capabilities.

```text
Human
  ↓
Siri
  ↓
App Intent / Apple Integration
  ↓
@iRiel
  ↓
Context + Identity + Policy
  ↓
Capability
  ↓
Action
```

## Architectural Position

Siri does not become the canonical owner of identity, context, memory, or capabilities. It is an entry point into the Apple Integration Layer.

## Intent and Entity Resolution

```text
Human Request
      ↓
Siri
      ↓
Intent Resolution
      ↓
Entity Resolution
      ↓
Context Founder
      ↓
Canonical Entity / Intent
```

Context should help resolve references such as “open it” or “complete this” when confidence is sufficient.

## App Intents

App Intents provide the structured execution contract between Siri and iRiel capabilities.

```text
Siri
  ↓
App Intent
  ↓
Thin Adapter
  ↓
iRiel Capability
```

## Privacy and Authorization

Siri invocation does not bypass PRSL-AI policy.

```text
Siri Request
     ↓
Policy
     ↓
Authorization
     ↓
Capability
```

Sensitive operations may require explicit authorization.

## Contextual Continuity

System-level Siri interactions should preserve relevant entity and contextual relationships whenever technically and safely possible.

```text
Siri
  ↓
Entity
  ↓
Context
  ↓
@iRiel
  ↓
Capability
```

## AI Independence

Siri is an Apple interaction surface, not a mandatory intelligence provider for PRSL-AI. The iRiel Router remains responsible for selecting the appropriate intelligence or capability.

## Objective

**Siri provides the interaction surface. App Intents provide the contract. @iRiel provides the context and capability architecture.**
