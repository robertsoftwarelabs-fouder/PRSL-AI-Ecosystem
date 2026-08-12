# PRSL-AI AppEntity Architecture

## 1. Purpose

`AppEntity` is the Apple-facing representation of an entity that can participate in system interactions through App Intents and related Apple intelligence surfaces.

Within PRSL-AI, `AppEntity` is treated as a **projection of the canonical iRiel domain entity**, not as the source of truth.

```text
Canonical iRiel Entity
        ↓
Privacy / Exposure Policy
        ↓
Apple Projection
        ↓
AppEntity
        ↓
Apple System
```

## 2. Architectural Position

`AppEntity` belongs exclusively to the Apple Integration Layer.

```text
PRSL-AI
   │
   ├── Identity
   ├── Context
   ├── Memory
   ├── Orchestration
   ├── Router
   └── Policy
          │
          ▼
   Apple Integration
          │
          ▼
      AppEntity
```

The iRiel Core should not depend on Apple's `AppEntity` representation.

## 3. Canonical Entity Model

PRSL-AI maintains its own domain representation.

```text
iRiel Domain Entity
      │
      ├── Identifier
      ├── Type
      ├── State
      ├── Metadata
      ├── Relationships
      └── Permissions
```

The canonical entity may then be projected into Apple's representation.

```text
iRiel Entity
    ↓
Projection Layer
    ↓
AppEntity
```

## 4. AppEntity as a Projection

The Apple representation should expose only the information required by the Apple interaction surface.

```text
Canonical Entity
       ↓
Exposure Policy
       ↓
Field Selection
       ↓
Privacy Filtering
       ↓
AppEntity
```

Therefore:

```text
AppEntity
   ≠
Canonical Entity
```

Instead:

```text
AppEntity
   =
Apple Projection of iRiel Entity
```

## 5. Entity Identity

Every entity exposed through `AppEntity` should have a stable identifier.

```text
iRiel Entity
      ↓
Canonical Identifier
      ↓
AppEntity Identifier
```

The identifier should allow the Apple integration layer to resolve the entity back to the canonical iRiel representation.

```text
AppEntity ID
     ↓
Entity Resolution
     ↓
iRiel Entity
```

The identifier should not unnecessarily expose private information.

## 6. Entity Types

Potential iRiel entities may include:

```text
Person
Document
Task
Project
Device
Application
Conversation
Service
Location
Automation
Memory Reference
Capability
```

Only entities that provide meaningful system-level interaction should be exposed through `AppEntity`.

## 7. Entity Resolution

```text
Apple Request
      ↓
AppEntity Identifier
      ↓
EntityQuery
      ↓
iRiel Entity Store / Context
      ↓
Canonical Entity
      ↓
Policy Validation
      ↓
Resolved Entity
```

Resolution should be deterministic whenever possible.

## 8. Contextual Resolution

```text
User Request
      ↓
Apple Entity
      ↓
Identifier
      ↓
Context Founder
      ↓
Current Context
      ↓
Entity Resolution
      ↓
iRiel Entity
```

This allows contextual references to remain meaningful across system interactions.

## 9. AppEntity and App Intents

`AppEntity` provides the entity representation. `AppIntent` provides the operation.

```text
AppEntity
    │
    │ represents
    ▼
Domain Entity
    │
    │ consumed by
    ▼
AppIntent
    │
    │ executes
    ▼
iRiel Capability
```

## 10. Entity Display Representation

```text
Canonical Entity
      ↓
Display Projection
      ↓
Title
Subtitle
Visual Representation
      ↓
Apple UI
```

The display representation should expose enough information to distinguish the entity without unnecessarily revealing private metadata.

## 11. Privacy Boundary

```text
Canonical Entity
      ↓
Privacy Policy
      ↓
Exposure Decision
      ↓
AppEntity
```

Therefore:

```text
Entity Exists
      ≠
Entity Is Exposable
```

## 12. Access Control

```text
AppEntity Request
      ↓
Identity
      ↓
Authorization
      ↓
Privacy Policy
      ↓
Entity Resolution
```

If authorization fails, the integration layer should return an appropriate failure rather than exposing the canonical entity.

## 13. EntityQuery Relationship

```text
Apple System
      ↓
EntityQuery
      ↓
AppEntity
      ↓
iRiel Entity
```

`EntityQuery` provides the resolution mechanism. `AppEntity` provides the Apple-facing entity representation.

## 14. Entity Lifecycle

```text
Created
   ↓
Canonical Entity
   ↓
Eligible for Exposure
   ↓
AppEntity Projection
   ↓
Apple Discovery
   ↓
Entity Resolution
   ↓
Capability Execution
   ↓
Updated / Removed
```

Changes to the canonical entity should be reflected appropriately in its Apple projection.

## 15. Entity State

```text
Entity
  ↓
Current State
  ↓
Projection
  ↓
AppEntity
```

Examples:

```text
Task → Pending
Task → Completed

Device → Available
Device → Offline

Document → Active
Document → Archived
```

## 16. Relationships Between Entities

```text
Person
   ↓
Project
   ↓
Task
   ↓
Document
```

These relationships should remain canonical within the iRiel domain. Apple-facing representations should expose only relationships necessary for the relevant system experience.

## 17. Context and Entity Identity

```text
Context
   ↓
Entity Identifier
   ↓
Canonical Entity
   ↓
Current State
   ↓
Contextual Meaning
```

## 18. Entity Projection and Memory

```text
Memory
   ↓
Entity Reference
   ↓
Canonical Entity
   ↓
AppEntity Projection
```

Memory should not be duplicated merely because an entity is exposed through Apple.

## 19. Entity Projection and Resonance

```text
Human
  ↕
Context
  ↕
Entity
  ↕
@iRiel
  ↕
AppEntity
  ↕
Apple System
```

## 20. AI-Agnostic Architecture

```text
AppEntity
    ↓
AppIntent
    ↓
iRiel Core
    ↓
Router
    ↓
Capability
```

Therefore:

```text
AppEntity
   ≠
Intelligence Provider
```

## 21. Platform Independence

```text
                Canonical
iRiel Entity
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
    AppEntity      API         MCP
        │
      Apple
```

## 22. Failure Handling

Possible failures include:

```text
Entity Not Found
Identifier Invalid
Entity Removed
Permission Denied
Context Expired
Entity No Longer Exposable
Integration Failure
```

The Apple-facing layer should translate these conditions into appropriate system-level results without exposing unnecessary implementation details.

## 23. Implementation Principle

```text
Canonical Domain Entity
        ↓
Stable Identifier
        ↓
Privacy / Exposure Policy
        ↓
Apple Projection
        ↓
AppEntity
        ↓
EntityQuery / AppIntent
        ↓
Apple System
```

## 24. Architectural Objective

The objective is to allow iRiel entities to participate in Apple's system intelligence ecosystem while preserving domain independence, privacy, contextual continuity, and platform portability.

`AppEntity` is therefore the **Apple-facing identity projection of an iRiel entity**.

**The domain owns the entity. Apple receives the projection.**
