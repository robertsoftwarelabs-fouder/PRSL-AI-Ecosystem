# PRSL-AI Contextual UI Architecture

## Purpose

Contextual UI defines how relevant interface state participates in PRSL-AI contextual intelligence.

```text
Human
  ↓
UI Interaction
  ↓
UI Context
  ↓
Context Founder
  ↓
Unified Context
  ↓
@iRiel
  ↓
Capability / Action
```

The UI is a source of contextual signals, not the owner of contextual intelligence.

## UI Context Model

```text
Current Application
       +
Current Scene / View
       +
Focused Element
       +
Selected Entity
       +
Available Actions
       +
Interaction State
       ↓
UI Context
```

Only contextually relevant signals should become active context.

## Context Founder

```text
UI
 ↓
UI Signals
 ↓
Normalization
 ↓
Context Founder
 ↓
Context Composition
 ↓
Unified Context
```

Context Founder remains the canonical contextual intelligence subsystem.

## Intent and References

Explicit human intent has priority. UI context assists interpretation without silently overriding it.

```text
Human Intent
      +
UI Context
      ↓
Context Founder
      ↓
Resolved Meaning
```

References such as “open this”, “send it”, or “continue here” may resolve against active UI context when confidence is sufficient. Ambiguity must trigger clarification rather than unsafe guessing.

## Entity and App Intent Integration

```text
Current UI Entity
      ↓
Canonical Entity Identifier
      ↓
AppEntity
      ↓
Apple System
```

and:

```text
UI Context
     ↓
Entity / Action
     ↓
App Intent
     ↓
iRiel Capability
```

## Privacy

```text
Visible
  ≠
Collectable
  ≠
Shareable
  ≠
Memorizable
```

Every transition is governed by policy. Minimum necessary contextual exposure is the default.

## Memory

```text
UI Event
   ↓
Context Evaluation
   ↓
Potential Memory Event
   ↓
Memory Policy
   ↓
Optional Retention
```

UI state is not automatically memory.

## Accessibility and Human Control

The same canonical context should support voice, touch, keyboard, assistive technologies, and other interaction modalities.

Context may inform adaptation, but it does not replace consent or human control.

## Continuity and Recovery

```text
iPhone / iPad / Mac / Web
          ↓
       Context
          ↓
       @iRiel
```

Reasonable interruptions may use context snapshots or history for recovery, subject to validation and policy.

## AI and Platform Independence

```text
UI
 ↓
Context Founder
 ↓
iRiel Core
 ↓
Router
 ↓
Capability
```

Apple-specific UI APIs are adapters to the canonical contextual architecture.

## Objective

**The interface shows the current state. Context gives that state meaning. @iRiel connects the two.**
