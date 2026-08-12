# PRSL-AI AppEntity Architecture

## Purpose

`AppEntity` is the Apple-facing representation of a canonical iRiel entity.

```text
Canonical iRiel Entity
        ↓
Apple Projection
        ↓
AppEntity
        ↓
Apple System
```

Apple does not become the owner of the underlying entity.

## Identity

Entity identity must remain stable across system references and resolve back to the canonical domain.

```text
Canonical ID
    ↓
AppEntity ID
    ↓
System Reference
    ↓
Entity Resolution
    ↓
Canonical Entity
```

Identifiers must not contain sensitive information.

## Representation

An AppEntity should expose only the properties necessary for Apple system discovery, display, resolution, and authorized interaction.

```text
Canonical Entity
      ↓
Privacy / Exposure Policy
      ↓
AppEntity Representation
```

## Resolution

AppEntity works with `EntityQuery` to resolve concrete entities. Resolution failures must remain isolated from the canonical domain.

## Context

An AppEntity can provide an anchor for Context Founder:

```text
AppEntity
   ↓
Canonical Entity
   ↓
Context Founder
   ↓
Unified Context
```

## Actions

AppEntity may participate in App Intent parameters and actions. Execution remains delegated to iRiel capabilities.

```text
AppEntity
   ↓
App Intent
   ↓
iRiel Capability
```

## Privacy and Independence

Availability of an AppEntity does not imply authorization to access all underlying data. The representation remains an Apple adapter over a platform-independent canonical model.

**AppEntity describes the entity to Apple; iRiel remains the owner of the entity.**
