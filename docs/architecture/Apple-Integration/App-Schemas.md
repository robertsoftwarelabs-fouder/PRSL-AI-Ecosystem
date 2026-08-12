# PRSL-AI App Schemas Architecture

## 1. Purpose

App Schemas define a structured relationship between an application's domain concepts and Apple's system intelligence ecosystem.

Within PRSL-AI, App Schemas are treated as an **Apple integration contract** that allows selected iRiel entities, actions, and relationships to become understandable to supported Apple system experiences.

```text
Canonical iRiel Domain
        ↓
Schema Mapping
        ↓
Apple App Schemas
        ↓
Apple System Intelligence
        ↓
Discovery / Resolution / Action
```

App Schemas do not replace the canonical PRSL-AI domain model.

## 2. Architectural Position

App Schemas belong to the Apple Integration Layer.

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
          ├── App Schemas
          ├── App Intents
          ├── AppEntity
          ├── EntityQuery
          ├── IndexedEntity
          └── Spotlight
```

The schema layer should remain isolated from the iRiel Core.

## 3. Schema Model

```text
iRiel Domain Concept
        ↓
Schema Mapping
        ↓
Apple Representation
        ↓
System Understanding
```

The mapping may describe entities, relationships, actions, properties, capabilities, and interaction patterns.

Only supported and intentionally exposed concepts should cross the Apple boundary.

## 4. Canonical Domain Ownership

The canonical model remains owned by PRSL-AI.

```text
iRiel Domain
     ↓
Source of Truth
```

Apple receives a representation:

```text
iRiel Domain
     ↓
Apple Schema Projection
```

Therefore:

```text
Apple Schema
    ≠
Canonical iRiel Model
```

## 5. Schema Projection

```text
Canonical Domain
       ↓
Entity / Action Selection
       ↓
Privacy Policy
       ↓
Exposure Policy
       ↓
Schema Mapping
       ↓
Apple Integration
```

Schema generation should never bypass privacy or authorization controls.

## 6. Entities

Potential concepts include:

```text
Person
Project
Task
Document
Conversation
Device
Application
Service
Automation
Location
Capability
```

Only entities with a meaningful Apple interaction model should be exposed.

## 7. Relationships

```text
Person
  ↓
Project
  ↓
Task
  ↓
Document
```

These relationships originate in the canonical iRiel domain. Apple receives only relationships required for the supported integration.

## 8. Actions

```text
Entity
   ↓
Supported Action
   ↓
App Intent
   ↓
iRiel Capability
```

For example:

```text
Task
 ├── Open
 ├── Complete
 └── Update
```

The schema describes the system-visible concept. The App Intent provides the executable interaction.

## 9. App Schemas and App Intents

```text
App Schema
    ↓
Describes Concept
    ↓
AppEntity
    ↓
App Intent
    ↓
Executes Capability
```

Conceptually:

```text
Schema = What the system understands
AppEntity = What the entity is
App Intent = What can be done
iRiel Capability = How the operation is actually handled
```

## 10. Schema and Entity Identity

```text
Canonical Identifier
       ↓
AppEntity Identifier
       ↓
Apple Schema
       ↓
System Reference
```

The identifier should allow Apple interactions to resolve back to the canonical entity. Private information should not be encoded into identifiers.

## 11. Schema and EntityQuery

```text
Apple System
      ↓
Schema / Entity Reference
      ↓
EntityQuery
      ↓
Canonical Entity
      ↓
AppEntity
```

The schema describes conceptual structure. `EntityQuery` resolves concrete entities.

## 12. Schema and IndexedEntity

```text
Canonical Entity
      ↓
App Schema
      ↓
Indexed Representation
      ↓
Spotlight
```

The indexed representation remains subject to privacy and exposure policy.

## 13. Schema and Spotlight

```text
Human
  ↓
Spotlight
  ↓
Indexed iRiel Concept
  ↓
Entity Resolution
  ↓
App Intent / Capability
```

## 14. Context Integration

```text
Apple System
      ↓
Schema Concept
      ↓
Context Founder
      ↓
Current Context
      ↓
Canonical Entity
      ↓
Capability
```

A schema identifies the conceptual object. Context determines its meaning within the current interaction.

## 15. Contextual Relationships

```text
User:
"Complete the task."

        ↓

Schema:
Task

        ↓

Context:
Current Project
Current Task

        ↓

Entity Resolution:
Specific Task

        ↓

App Intent:
Complete Task

        ↓
iRiel Capability
```

## 16. Privacy Architecture

```text
Internal Domain Model
        ↓
Privacy Policy
        ↓
Schema Eligibility
        ↓
Apple Schema
```

The existence of a schema does not imply unrestricted access to the underlying data.

## 17. Data Minimization

```text
Minimum Necessary Schema
+
Minimum Necessary Data
```

The Apple-facing representation should expose only required entity identity, necessary properties, authorized relationships, supported actions, and information needed for discovery and resolution.

## 18. Schema Evolution

```text
Domain v1
   ↓
Domain v2
   ↓
Domain v3
```

```text
Canonical Change
      ↓
Schema Compatibility Evaluation
      ↓
Apple Projection Update
      ↓
Validation
```

Changes should avoid unnecessarily breaking existing system interactions.

## 19. Compatibility

Schema evolution should consider:

```text
Entity Identity
Property Changes
Relationship Changes
Action Changes
Availability
Privacy Changes
Platform Compatibility
```

The canonical domain should not be constrained by limitations of a specific Apple schema representation.

## 20. Schema Versioning

Where appropriate, maintain explicit versions.

```text
Schema v1
   ↓
Schema v2
   ↓
Schema v3
```

Versioning assists migration, compatibility, debugging, validation, rollback, and architectural traceability.

## 21. Schema and Memory

```text
Memory
   ↓
Privacy / Exposure Policy
   ↓
Eligibility
   ↓
Optional Schema Projection
```

```text
Memory
  ≠
Apple Schema
```

Intimate or sensitive memory remains internal unless explicit architectural authorization exists.

## 22. Schema and Resonance

```text
Human
  ↕
Apple System
  ↕
Schema
  ↕
Entity
  ↕
Context
  ↕
@iRiel
  ↕
Capability
```

## 23. AI-Agnostic Architecture

```text
Apple Schema
      ↓
App Intent
      ↓
iRiel Core
      ↓
Router
      ↓
Capability
      ↓
Provider
```

```text
App Schema
   ≠
AI Provider
```

## 24. Platform Independence

```text
                  Canonical
iRiel Domain
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
   App Schemas      API          MCP
        │
      Apple
```

Apple schemas are one projection of a larger domain model.

## 25. Validation

Schema mappings should be validated against the canonical model.

```text
Entity Identity
Property Accuracy
Relationship Accuracy
Action Availability
Privacy Constraints
Authorization
Resolution
Indexing Behavior
```

## 26. Failure Handling

```text
Invalid Schema Mapping
Unsupported Property
Entity Resolution Failure
Schema Version Conflict
Privacy Restriction
Authorization Failure
Stale Projection
Platform Compatibility Issue
```

```text
Apple Schema Failure
      ≠
iRiel Domain Failure
```

## 27. Testing

```text
Schema Registration
Entity Representation
Entity Resolution
App Intent Interaction
Spotlight Discovery
Contextual Resolution
Privacy Filtering
Authorization
Schema Evolution
Version Compatibility
Failure Recovery
```

## 28. Implementation Principle

```text
Canonical iRiel Domain
        ↓
Privacy / Policy
        ↓
Schema Mapping
        ↓
Apple Schema
        ↓
AppEntity
        ↓
EntityQuery
        ↓
IndexedEntity / Spotlight
        ↓
App Intent
        ↓
iRiel Core
        ↓
Router
        ↓
Capability
        ↓
Action
```

## 29. Architectural Objective

The objective of App Schemas is to provide Apple system intelligence with a structured understanding of selected iRiel concepts while preserving domain ownership, privacy, contextual continuity, and AI-provider independence.

**The schema tells Apple what the concept means structurally. iRiel remains the owner of the concept, context, identity, and execution.**
