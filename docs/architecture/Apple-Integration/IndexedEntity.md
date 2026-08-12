# PRSL-AI IndexedEntity Architecture

## 1. Purpose

`IndexedEntity` defines how selected iRiel entities can participate in Apple's indexed system experiences.

Within PRSL-AI, indexing is treated as a **controlled projection of canonical entities into Apple's discovery layer**.

```text
Canonical iRiel Entity
        ↓
Privacy / Exposure Policy
        ↓
Index Projection
        ↓
IndexedEntity
        ↓
Apple System Index
        ↓
Discovery / Resolution
```

Indexing does not transfer ownership of the canonical entity to Apple.

## 2. Architectural Position

`IndexedEntity` belongs to the Apple Integration Layer.

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
          ├── AppEntity
          ├── EntityQuery
          ├── IndexedEntity
          ├── App Intents
          └── Spotlight
```

## 3. Indexing Model

```text
iRiel Entity
      ↓
Eligibility Evaluation
      ↓
Privacy Policy
      ↓
Index Projection
      ↓
IndexedEntity
      ↓
Apple Index
      ↓
System Discovery
```

Only entities appropriate for system discovery should be indexed.

## 4. Indexed Entity vs Canonical Entity

```text
Canonical Entity
      ≠
IndexedEntity
```

Instead:

```text
IndexedEntity
      =
Apple Index Projection
of a Canonical iRiel Entity
```

## 5. Index Eligibility

Eligibility may depend on:

```text
Entity Type
User Intent
Privacy Policy
Entity State
Interaction Frequency
System Relevance
Current Availability
User Authorization
```

```text
Entity
  ↓
Should Be Discoverable?
  ↓
Yes / No
```

Privacy takes precedence over convenience.

## 6. Privacy Boundary

```text
Entity Exists
      ≠
Entity Should Be Indexed
```

```text
Canonical Entity
      ↓
Privacy Policy
      ↓
Exposure Decision
      ↓
Field Filtering
      ↓
IndexedEntity
```

## 7. Minimum Necessary Indexing

An indexed representation should contain only information required for identification, discovery, disambiguation, supported actions, and relevant system experiences.

```text
Index Data
⊂
Authorized Entity Data
```

## 8. Entity Identity

```text
Canonical Identifier
       ↓
Index Identifier
       ↓
Apple Index
```

The identifier should allow the indexed result to resolve back to the canonical iRiel entity without exposing unnecessary personal information.

## 9. Index Projection

```text
Canonical Entity
      ↓
Select Indexable Fields
      ↓
Apply Privacy Rules
      ↓
Generate Search Representation
      ↓
Generate Entity Metadata
      ↓
IndexedEntity
```

## 10. Indexed Data

A conceptual indexed representation may contain:

```text
Identifier
Title
Subtitle
Entity Type
Keywords
Relevant Metadata
Supported Actions
Availability
```

## 11. Search and Discovery

```text
Human
  ↓
System Search
  ↓
Indexed Entity
  ↓
Entity Resolution
  ↓
Canonical iRiel Entity
  ↓
Capability
```

## 12. IndexedEntity and AppEntity

```text
IndexedEntity
     ↓
Discovery
     ↓
AppEntity
     ↓
Resolution
     ↓
Canonical Entity
```

Conceptually:

```text
IndexedEntity = discoverability
AppEntity = typed system representation
Canonical Entity = source of truth
```

## 13. IndexedEntity and EntityQuery

```text
Apple Search
      ↓
IndexedEntity
      ↓
Identifier
      ↓
EntityQuery
      ↓
AppEntity
      ↓
Canonical Entity
```

## 14. Contextual Discovery and Resolution

```text
Search Signal
      +
Current Context
      ↓
Entity Relevance
      ↓
Indexed Entity
```

After discovery:

```text
Indexed Entity
      ↓
Identifier
      ↓
Context Founder
      ↓
Current Context
      ↓
Canonical Entity
```

Contextual relevance must not bypass privacy boundaries.

## 15. Index Lifecycle

```text
Entity Created
      ↓
Eligibility Evaluation
      ↓
Index Projection
      ↓
Indexed
      ↓
Updated
      ↓
Reindexed
      ↓
Removed / Invalidated
```

## 16. Index Invalidation

Possible causes include:

```text
Entity Deleted
Entity Renamed
Entity State Changed
Permission Changed
Privacy Policy Changed
Entity No Longer Relevant
User Revoked Access
```

## 17. Privacy Revocation

```text
Privacy Policy Change
        ↓
Exposure Re-evaluation
        ↓
Index Update / Removal
        ↓
Apple System
```

## 18. Index and Memory

```text
Memory
   ↓
Privacy / Exposure Policy
   ↓
Eligibility
   ↓
Optional Index Projection
```

```text
Memory
  ≠
Search Index
```

Sensitive memory should remain outside system indexing unless explicitly authorized and architecturally justified.

## 19. Index and Resonance

```text
Human
  ↕
Discovery
  ↕
Indexed Entity
  ↕
AppEntity
  ↕
Canonical Entity
  ↕
Context
  ↕
@iRiel
```

## 20. AI-Agnostic Architecture

```text
IndexedEntity
      ↓
Entity Resolution
      ↓
iRiel Core
      ↓
Router
      ↓
Capability
      ↓
Provider / Tool
```

The indexed entity remains provider-independent.

## 21. Platform Independence

```text
             Canonical Entity
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
   Apple Index      API         MCP
        │
 IndexedEntity
```

## 22. Security

Indexing should consider authorization, privacy, data minimization, identifier security, stale data, revocation, and access scope.

The index should never become an unintended secondary data store for private iRiel information.

## 23. Performance

Important considerations include:

```text
Efficient Index Updates
Bounded Metadata
Incremental Reindexing
Stable Identifiers
Fast Resolution
Graceful Failure
```

## 24. Failure Handling

```text
Index Update Failure
Entity Resolution Failure
Stale Index
Invalid Identifier
Permission Revocation
Entity Deletion
Integration Failure
```

```text
Index Failure
      ≠
Domain Failure
```

## 25. Testing

```text
Index Creation
Index Updates
Index Removal
Identifier Stability
Search Discovery
Entity Resolution
Privacy Filtering
Authorization
Revocation
Stale Data
Contextual Resolution
Failure Recovery
```

## 26. Implementation Principle

```text
Canonical iRiel Entity
        ↓
Eligibility
        ↓
Privacy / Policy
        ↓
Index Projection
        ↓
IndexedEntity
        ↓
Apple Index
        ↓
Discovery
        ↓
EntityQuery
        ↓
AppEntity
        ↓
Canonical Entity
        ↓
iRiel Capability
```

## 27. Architectural Objective

The objective of `IndexedEntity` is to make selected iRiel entities discoverable through Apple's system experiences while preserving domain ownership, privacy, contextual continuity, and platform independence.

`IndexedEntity` is therefore the **controlled discovery projection of an iRiel entity into Apple's indexing layer**.

**Discovery may happen in Apple. Identity and meaning remain with iRiel.**
