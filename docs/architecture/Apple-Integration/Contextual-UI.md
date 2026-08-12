# PRSL-AI Contextual UI Architecture

## 1. Purpose

Contextual UI defines how user-interface state participates in the PRSL-AI contextual intelligence architecture.

The interface is not treated as an isolated presentation layer.

Relevant UI state can become a contextual signal that helps @iRiel understand:

* what the human is currently viewing;
* which entity is active;
* what action is available;
* what interaction is in progress;
* what information is relevant to the current task.

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

## 2. Architectural Position

Contextual UI belongs to the Apple Integration Layer while remaining connected to the canonical Context Founder architecture.

```text
PRSL-AI
   │
   ├── Identity
   ├── Context
   ├── Memory
   ├── Orchestration
   ├── Router
   └── Privacy / Policy
          │
          ▼
   Apple Integration
          │
          ├── Contextual UI
          ├── App Intents
          ├── AppEntity
          ├── EntityQuery
          ├── App Schemas
          └── Spotlight
```

The UI is a source of contextual signals, not the owner of contextual intelligence.

## 3. UI Context Model

```text
Current Application
       +
Current Scene
       +
Current View
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

UI Context becomes one component of the unified contextual model.

## 4. UI Context and Context Founder

Context Founder remains the canonical owner of contextual intelligence.

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

The UI should not independently maintain a second contextual intelligence system.

## 5. Contextual UI Signals

Potential signals include:

```text
Current Application
Current Screen
Current View
Selected Entity
Focused Control
Visible Entity
Navigation State
Editing State
Modal State
Available Actions
Interaction Mode
```

Only signals that provide meaningful contextual value should be captured.

## 6. Contextual Relevance

```text
UI Signal
   ↓
Relevance Evaluation
   ↓
Context Founder
   ↓
Active Context
```

Relevance may consider intent, entity relevance, interaction relevance, temporal relevance, privacy policy, and confidence.

## 7. UI Context and Human Intent

Explicit human intent remains the highest-priority signal.

```text
Human Intent
      ↓
      +
UI Context
      ↓
Context Founder
      ↓
Resolved Meaning
```

UI context should help interpret intent rather than silently override it.

Example:

```text
Human:
"Open it."

UI Context:
Current document = Project Plan

Resolved reference:
"it" → Project Plan
```

## 8. Entity Context

```text
Current UI
     ↓
Selected Entity
     ↓
Entity Identifier
     ↓
Context Founder
     ↓
Canonical iRiel Entity
```

## 9. AppEntity Integration

```text
UI
 ↓
Canonical Entity
 ↓
AppEntity
 ↓
Apple System
```

The canonical entity remains outside Apple's representation.

## 10. App Intent Integration

```text
UI Context
     ↓
Entity / Action
     ↓
App Intent
     ↓
iRiel Capability
     ↓
Action
```

## 11. Contextual References

Natural language frequently contains contextual references:

```text
"Open this."
"Change that."
"Send it."
"Use the selected one."
"Continue here."
```

```text
Human Reference
      ↓
UI Context
      ↓
Entity Resolution
      ↓
Canonical Entity
      ↓
Action
```

## 12. Contextual Resolution Pipeline

```text
Human Intent
      ↓
Reference Detection
      ↓
UI Context
      ↓
Entity Resolution
      ↓
Context Validation
      ↓
Privacy / Policy
      ↓
Resolved Intent
      ↓
Capability
```

Ambiguous references should not be silently resolved when confidence is insufficient.

## 13. UI State and Memory

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

```text
UI State
  ≠
Memory
```

Memory retention must remain explicitly governed by PRSL-AI memory and privacy policies.

## 14. UI State and Privacy

```text
Visible
  ≠
Collectable
  ≠
Shareable
  ≠
Memorizable
```

Each transition requires an appropriate policy decision.

```text
UI Context
     ↓
Privacy Policy
     ↓
Authorized Context
```

## 15. Contextual UI and Accessibility

Accessibility is an architectural concern rather than a cosmetic layer.

Contextual UI should account for:

```text
Voice
Touch
Keyboard
Assistive Technologies
Visual Interaction
Reduced Interaction Complexity
```

The same canonical context should be available regardless of interaction modality.

```text
Voice ─────┐
Touch ─────┤
Keyboard ──┼──→ Context Founder
Assistive ─┤
Other ─────┘
```

## 16. Neuro-Inclusive Interaction

Contextual interfaces should minimize unnecessary cognitive load.

The architecture should support:

```text
Predictable State
Clear Feedback
Stable Interaction
Reduced Repetition
Context Preservation
Recoverable Actions
```

## 17. Context Continuity

```text
iPhone
  ↓
@iRiel
  ↓
Context
  ↓
iPad
  ↓
Mac
  ↓
Web
  ↓
External Service
```

The interface changes. The relevant contextual relationship can remain continuous. This is a core component of iRiel Resonance.

## 18. Context Recovery

```text
Active UI Context
      ↓
Interruption
      ↓
Context Snapshot / History
      ↓
Context Recovery
      ↓
Validation
      ↓
Restored Context
```

Recovery should restore only the minimum sufficient context required for safe continuation.

## 19. Contextual UI and Spotlight

```text
Spotlight
    ↓
Entity / Action
    ↓
Context Founder
    ↓
Current Context
    ↓
UI
```

## 20. Contextual UI and App Schemas

```text
App Schema
    ↓
Entity
    ↓
UI Representation
    ↓
Context Founder
```

The schema defines the structured concept. The UI provides its current interaction state.

## 21. Contextual UI and iRiel Resonance

```text
Human
  ↕
UI
  ↕
Context
  ↕
@iRiel
  ↕
Memory
  ↕
Intelligence
  ↕
Capability
  ↕
Action
```

## 22. Adaptive UI

The architecture may allow UI behavior to adapt to contextual state:

```text
Relevant Actions
Relevant Information
Contextual Suggestions
Interaction Continuity
Accessibility Adjustments
Reduced Repetition
```

Adaptation must remain policy-controlled and should not infer that contextual signals authorize automatic interface changes.

## 23. Human Control

```text
Context
  ↓
Possible Adaptation
  ↓
Policy
  ↓
Human-Compatible Action
```

The principle is:

```text
Context informs adaptation.

Context does not replace consent.
```

## 24. AI-Agnostic Architecture

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
 ↓
Selected Intelligence
```

The UI context architecture remains provider-independent.

## 25. Platform Independence

```text
                  Context Founder
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
   Apple UI          Web UI       Other UI
        │
 Context Projection
```

Apple-specific APIs are adapters to the canonical contextual architecture.

## 26. Failure Handling

```text
Missing UI Context
Stale Context
Entity Resolution Failure
Permission Denied
Context Expired
UI State Changed
Integration Failure
```

```text
UI Context Failure
      ≠
Context Founder Failure
```

The system should degrade gracefully and request clarification when necessary.

## 27. Testing

```text
UI State Detection
Entity Selection
Context Propagation
Reference Resolution
App Intent Execution
Privacy Filtering
Accessibility Modes
Context Recovery
Interruption
Cross-Device Continuity
Ambiguous References
Failure Recovery
```

## 28. Implementation Principle

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
Identity + Memory + Policy
  ↓
@iRiel
  ↓
Orchestration
  ↓
Router
  ↓
Capability
  ↓
Adaptive UI / Action
  ↓
Human
```

The UI remains a contextual surface rather than becoming the owner of contextual intelligence.

## 29. Architectural Objective

The objective of Contextual UI is to allow interface state, human interaction, and contextual intelligence to operate as a continuous system while preserving privacy, accessibility, human control, and platform independence.

**The interface shows the current state. Context gives that state meaning. @iRiel connects the two.**
