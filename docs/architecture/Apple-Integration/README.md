# Apple Integration

## Purpose

This directory documents how PRSL-AI integrates with the Apple ecosystem.

Apple is treated as an **integration surface**, not as the owner of the PRSL-AI architecture.

The integration layer allows @iRiel to participate in supported Apple system experiences while preserving the independence of the canonical PRSL-AI domain, context, memory, privacy, and intelligence architecture.

---

## Architecture

The conceptual relationship is:

```text
                    PRSL-AI
                       │
                       ▼
                 @iRiel Core
                       │
                       ▼
             Apple Integration Layer
                       │
       ┌───────────────┼────────────────┐
       ▼               ▼                ▼
    Entities         Actions          Context
       │               │                │
       ▼               ▼                ▼
  AppEntity        App Intents     Contextual UI
       │               │                │
       └───────────────┼────────────────┘
                       ▼
                Apple System
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
      Spotlight       Siri     Apple Intelligence
```

---

## Documentation

### Apple Intelligence

`Apple-Intelligence.md`

Documents the architectural relationship between PRSL-AI and Apple's system intelligence capabilities.

### Siri

`Siri.md`

Documents Siri as an interaction surface for iRiel capabilities and contextual actions.

### App Intents

`App-Intents.md`

Documents the action and capability integration layer used to expose structured iRiel operations to Apple system experiences.

### AppEntity

`AppEntity.md`

Documents the Apple-facing representation of canonical iRiel entities.

### EntityQuery

`EntityQuery.md`

Documents entity resolution between Apple system references and canonical iRiel entities.

### IndexedEntity

`IndexedEntity.md`

Documents entity indexing and system discoverability.

### Spotlight

`Spotlight.md`

Documents Spotlight integration and the transition from system discovery to structured iRiel interaction.

### App Schemas

`App-Schemas.md`

Documents schema-based representation of iRiel domain concepts within the Apple ecosystem.

### Contextual UI

`Contextual-UI.md`

Documents how interface state becomes contextual information that can participate in Context Founder and iRiel interactions.

---

## Architectural Principles

The Apple Integration Layer follows several principles.

### 1. Domain Independence

The canonical PRSL-AI domain remains independent from Apple's representations.

```text
Canonical iRiel Domain
        ↓
Apple Projection
        ↓
Apple System
```

Apple representations are projections, not the source of truth.

### 2. AI Agnosticism

Apple integration must not create a hard dependency on Apple Intelligence.

```text
Apple Integration
        ↓
iRiel Core
        ↓
Router
        ↓
Selected Intelligence
```

The selected intelligence may be on-device, local, Apple, OpenAI, Anthropic, Google, MCP, an API, or another supported capability.

### 3. Privacy by Design

Information exposed to Apple system services must pass through PRSL-AI privacy and policy boundaries.

```text
Canonical Data
      ↓
Privacy Policy
      ↓
Exposure Policy
      ↓
Apple Projection
```

Availability does not imply authorization.

### 4. Contextual Continuity

Apple system interactions should preserve contextual relationships whenever technically and safely possible.

```text
System Interaction
       ↓
Entity
       ↓
Context
       ↓
@iRiel
       ↓
Capability
```

### 5. Human-Centered Interaction

Apple technologies are used to reduce friction between the human and the personal intelligence environment.

The objective is not simply to expose more functionality.

The objective is to make relevant capabilities available at the right contextual moment.

---

## Integration Boundary

The architectural boundary is:

```text
┌──────────────────────────────────┐
│          PRSL-AI Core            │
│                                  │
│ Identity                         │
│ Context                          │
│ Memory                           │
│ Orchestration                    │
│ Router                           │
│ Privacy                          │
│ Accessibility                   │
│                                  │
└───────────────┬──────────────────┘
                │
                ▼
┌──────────────────────────────────┐
│      Apple Integration Layer     │
│                                  │
│ App Intents                      │
│ AppEntity                        │
│ EntityQuery                      │
│ IndexedEntity                    │
│ App Schemas                      │
│ Spotlight                        │
│ Siri                             │
│ Contextual UI                    │
│ Apple Intelligence              │
│                                  │
└───────────────┬──────────────────┘
                │
                ▼
        Apple System Services
```

The integration boundary prevents Apple-specific implementation details from propagating unnecessarily into the Core.

---

## Relationship to Context Founder

Context Founder remains the canonical contextual intelligence subsystem.

Apple may provide contextual signals such as:

```text
Current Application
Current Entity
Current View
Available Action
System State
Interaction State
```

These signals enter the PRSL-AI architecture through controlled integration boundaries.

```text
Apple Context
      ↓
Apple Adapter
      ↓
Context Founder
      ↓
Unified Context
      ↓
@iRiel
```

---

## Relationship to Memory

Apple system state is not automatically memory.

```text
Apple Signal
     ↓
Context
     ↓
Policy Evaluation
     ↓
Optional Memory Event
```

Memory retention remains governed by PRSL-AI memory and privacy policies.

---

## Relationship to iRiel Resonance

The Apple Integration Layer contributes to iRiel Resonance by connecting system-level interactions with the continuous personal intelligence environment.

```text
Human
  ↕
Apple System
  ↕
Apple Integration
  ↕
@iRiel
  ↕
Context
  ↕
Memory
  ↕
Intelligence
  ↕
Capability
```

The purpose is continuity rather than platform dependency.

---

## Implementation Status

This documentation describes the **target and architectural model**.

A documented integration concept must not be interpreted as an implemented feature.

Implementation status must be verified against repository evidence.

```text
Concept
   ↓
Design
   ↓
Implementation
   ↓
Validation
   ↓
Operational Capability
```

Only repository evidence should be used to classify a capability as implemented.

---

## Directory Structure

```text
Apple-Integration/
│
├── Apple-Intelligence.md
├── Siri.md
├── App-Intents.md
├── AppEntity.md
├── EntityQuery.md
├── IndexedEntity.md
├── Spotlight.md
├── App-Schemas.md
├── Contextual-UI.md
└── README.md
```

---

## Objective

The Apple Integration Layer exists to make PRSL-AI interoperable with Apple's ecosystem without surrendering architectural ownership.

The intended relationship is:

```text
Human
   ↓
@iRiel
   ↓
Personal Intelligence Environment
   ↓
Apple Integration
   ↓
Apple System
```

Apple provides capabilities and system surfaces.

**PRSL-AI provides the personal intelligence architecture that gives those capabilities context, continuity, privacy, and purpose.**
