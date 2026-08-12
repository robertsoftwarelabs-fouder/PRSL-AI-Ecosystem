# PRSL-AI App Schemas Architecture

## Purpose

App Schemas define a structured relationship between canonical iRiel domain concepts and Apple's system intelligence ecosystem.

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

App Schemas are projections of the canonical domain, not its source of truth.

## Architectural Position

App Schemas belong to the Apple Integration Layer alongside App Intents, AppEntity, EntityQuery, IndexedEntity, and Spotlight.

```text
iRiel Domain
     ↓
Privacy / Exposure Policy
     ↓
Schema Mapping
     ↓
Apple Representation
```

## Entities, Relationships and Actions

Schemas may expose selected:

- entities;
- relationships;
- properties;
- actions;
- capabilities;
- interaction patterns.

Only intentionally exposed concepts cross the Apple boundary.

## Identity

```text
Canonical Identifier
       ↓
AppEntity Identifier
       ↓
Apple Schema
       ↓
System Reference
```

Identifiers must remain stable and must not encode private information.

## Entity Resolution

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

## Privacy

Schema generation must never bypass privacy or authorization controls.

```text
Internal Domain Model
        ↓
Privacy Policy
        ↓
Schema Eligibility
        ↓
Apple Schema
```

Minimum necessary data and relationships should be exposed.

## Memory

```text
Memory
  ≠
Apple Schema
```

Memory becomes schema-visible only through explicit exposure policy.

## AI and Platform Independence

```text
Apple Schema
   ↓
App Intent
   ↓
iRiel Core
   ↓
Router
   ↓
Capability / Provider
```

Apple schemas do not create an AI-provider dependency and remain one projection of a platform-independent canonical domain.

## Validation and Failure Isolation

Validation covers identity, properties, relationships, actions, privacy, authorization, resolution, indexing, and compatibility.

```text
Apple Schema Failure
      ≠
iRiel Domain Failure
```

## Objective

**The schema tells Apple what the concept means structurally. iRiel remains the owner of the concept, context, identity, and execution.**
