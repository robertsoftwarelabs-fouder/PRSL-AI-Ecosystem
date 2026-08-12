# PRSL-AI EntityQuery Architecture

## Purpose

`EntityQuery` is the Apple integration boundary used to resolve Apple-facing entity references into canonical iRiel entities.

```text
Apple System
      ↓
Entity Reference
      ↓
EntityQuery
      ↓
Canonical Entity
      ↓
AppEntity
```

## Resolution Responsibilities

EntityQuery may support:

- identifier lookup;
- suggested entities;
- search / dynamic resolution;
- controlled failure handling.

It should not become a second source of truth.

## Canonical Ownership

```text
Canonical Domain
      ↓
Source of Truth

EntityQuery
      ↓
Resolver / Adapter
```

Apple identifiers must map back to stable canonical identifiers.

## Context Integration

Resolved entities may become contextual anchors:

```text
EntityQuery
    ↓
Canonical Entity
    ↓
Context Founder
    ↓
Unified Context
```

## Privacy

Queries must apply privacy, authorization, and exposure policy before returning entities.

```text
Query
 ↓
Policy
 ↓
Authorized Result
```

## Failure Handling

Invalid, stale, unauthorized, or ambiguous references should fail safely and must never corrupt canonical entities or context.

## Objective

**EntityQuery translates Apple references into canonical iRiel entities without transferring domain ownership to Apple.**
