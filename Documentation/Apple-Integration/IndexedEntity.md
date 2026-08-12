# PRSL-AI IndexedEntity Architecture

## Purpose

IndexedEntity defines the Apple-facing indexing and discoverability projection of selected canonical iRiel entities.

```text
Canonical Entity
      ↓
Privacy / Exposure Policy
      ↓
Indexed Representation
      ↓
Apple System Search
```

## Indexing Boundary

Indexing is a discoverability mechanism, not a transfer of domain ownership.

```text
Canonical iRiel Domain
        ↓
Apple Projection
        ↓
IndexedEntity
```

## Privacy

Only authorized, intentionally exposed information should enter the system index. Sensitive internal metadata remains outside the projection.

```text
Index Eligibility
      ↓
Privacy Policy
      ↓
Exposure Policy
      ↓
Index
```

## Lifecycle

Index entries may become stale as canonical entities change. Updates and removal must preserve canonical identity and fail safely.

## Discovery

Indexed entities can provide a bridge from system discovery to structured interaction:

```text
Search
  ↓
Indexed Entity
  ↓
Entity Resolution
  ↓
AppEntity
  ↓
App Intent / Capability
```

## Independence

Indexing must not become a second canonical store or constrain the domain model to Apple limitations.

**IndexedEntity makes selected iRiel concepts discoverable; iRiel remains the source of truth.**
