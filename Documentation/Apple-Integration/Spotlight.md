# PRSL-AI Spotlight Architecture

## Purpose

Spotlight is an Apple system discovery surface for selected iRiel entities and capabilities.

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
  ↓
@iRiel
```

## Discovery Boundary

Spotlight should discover authorized projections of the canonical domain, not become the owner of those entities.

```text
Canonical Domain
      ↓
Privacy / Exposure Policy
      ↓
Apple Index
      ↓
Spotlight
```

## Context

A Spotlight interaction can transition into application context while preserving entity identity.

```text
Spotlight
    ↓
Entity
    ↓
Context Founder
    ↓
Current Context
    ↓
UI / Capability
```

## Privacy

Indexing and discovery are policy-controlled. Search visibility does not imply unrestricted access to underlying data.

## Integration

Spotlight can act as an entry point into AppEntity, EntityQuery, App Intents, and Contextual UI without moving canonical business logic into Apple-specific code.

## Failure Isolation

Stale indexes, failed resolution, or unavailable actions must degrade safely and must not corrupt the canonical iRiel domain.

**Spotlight is a discovery surface; @iRiel remains the contextual and capability owner.**
