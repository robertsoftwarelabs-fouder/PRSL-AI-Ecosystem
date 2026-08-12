# PRSL-AI EntityQuery Architecture

## 1. Purpose

`EntityQuery` provides the Apple Integration Layer with a controlled mechanism for locating and resolving `AppEntity` representations.

Within PRSL-AI, `EntityQuery` is treated as a **resolution adapter** between Apple's system experiences and the canonical iRiel entity model.

```text
Apple System
      ↓
EntityQuery
      ↓
Apple Integration Layer
      ↓
Context / Policy
      ↓
Canonical iRiel Entity
      ↓
AppEntity Projection
```

`EntityQuery` does not own the canonical entity store.

## 2. Architectural Position

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
          ├── App Intents
          ├── AppEntity
          ├── EntityQuery
          └── Indexed Entities
```

## 3. Resolution Model

```text
Apple Request
      ↓
Entity Identifier / Search
      ↓
EntityQuery
      ↓
Context
      ↓
Policy
      ↓
Canonical Entity
      ↓
AppEntity
      ↓
Apple System
```

`EntityQuery` translates Apple's request into a controlled lookup against the canonical iRiel model.

## 4. Query Responsibilities

An `EntityQuery` may be responsible for:

```text
Identifier Lookup
String Search
Suggested Entities
Contextual Resolution
Entity Filtering
Entity Availability
```

The architectural responsibility remains to resolve an Apple-facing entity reference into the appropriate canonical iRiel entity.

## 5. Identifier Resolution

```text
AppEntity Identifier
       ↓
EntityQuery
       ↓
Canonical Identifier
       ↓
iRiel Entity
       ↓
AppEntity
```

## 6. Search Resolution

```text
Search Text
    ↓
EntityQuery
    ↓
Candidate Entities
    ↓
Filtering
    ↓
Ranking
    ↓
Resolved Entity
```

Search results should be limited to entities that the current interaction is authorized to expose.

## 7. Contextual Resolution

```text
Search / Reference
       +
Current Context
       ↓
EntityQuery
       ↓
Context Founder
       ↓
Candidate Resolution
       ↓
Canonical Entity
```

Context improves query precision without bypassing explicit user intent.

## 8. Context Founder Integration

`EntityQuery` should not independently reconstruct complete contextual state.

```text
EntityQuery
     ↓
Context Request
     ↓
Context Founder
     ↓
Relevant Context
     ↓
Entity Resolution
```

## 9. Privacy Boundary

```text
EntityQuery
     ↓
Query Scope
     ↓
Privacy Policy
     ↓
Authorization
     ↓
Eligible Entities
```

```text
Entity Exists
      ≠
Entity Query May Return It
```

## 10. Minimum Necessary Exposure

```text
Potential Entities
       ↓
Privacy Filtering
       ↓
Capability Filtering
       ↓
Context Filtering
       ↓
Eligible Results
```

## 11. EntityQuery and AppEntity

```text
EntityQuery
     │
     │ resolves
     ▼
AppEntity
     │
     │ represents
     ▼
Canonical iRiel Entity
```

`EntityQuery` provides resolution behavior. `AppEntity` provides representation. Neither becomes the canonical domain model.

## 12. EntityQuery and App Intents

```text
Apple System
      ↓
App Intent
      ↓
Entity Parameter
      ↓
EntityQuery
      ↓
AppEntity
      ↓
Canonical iRiel Entity
      ↓
Capability
```

## 13. Query Lifecycle

```text
Query Received
      ↓
Validate Request
      ↓
Establish Query Scope
      ↓
Apply Context
      ↓
Apply Privacy Policy
      ↓
Resolve Candidates
      ↓
Filter
      ↓
Rank
      ↓
Return AppEntity
```

## 14. Query Scope

Possible scopes include:

```text
Current Session
Current Task
Current Application
Current User
Authorized Workspace
Available Devices
Exposed Services
```

Scope should be determined before unrestricted entity lookup occurs.

## 15. Query Ranking

Signals may include:

```text
Exact Match
Context Match
Entity Type
Recency
Interaction History
Current State
User Intent
Confidence
```

Ranking must never override explicit authorization or privacy constraints.

## 16. Ambiguity

```text
Query
  ↓
Candidate A
Candidate B
Candidate C
```

The system should distinguish between high confidence and ambiguous results. When confidence is insufficient, it should prefer clarification rather than silently selecting the wrong entity.

## 17. Entity Availability

```text
Canonical Entity
      ↓
Availability Check
      ↓
Privacy / Policy
      ↓
Apple Exposure
```

Reasons may include permission, offline state, temporary unavailability, private state, deleted entity, expired context, or unsupported operation.

## 18. Query and Memory

```text
Query
  ↓
Context
  ↓
Authorized Memory Reference
  ↓
Entity Resolution
```

Memory access remains governed by the PRSL-AI memory and privacy architecture.

## 19. Query and Resonance

```text
Human
  ↕
Context
  ↕
Entity
  ↕
@iRiel
  ↕
EntityQuery
  ↕
Apple System
```

## 20. Performance

Important considerations include:

```text
Low Latency
Efficient Lookup
Bounded Result Sets
Caching Where Appropriate
Minimal Data Transfer
Graceful Failure
```

Expensive reasoning should not unnecessarily occur inside the Apple integration boundary.

## 21. AI-Agnostic Architecture

```text
EntityQuery
     ↓
Canonical Entity
     ↓
iRiel Core
     ↓
Router
     ↓
Capability
```

```text
EntityQuery
   ≠
AI Runtime
```

## 22. Platform Independence

```text
              Canonical Entity Model
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
   EntityQuery        API            MCP
        │
      Apple
```

## 23. Error Handling

```text
Invalid Identifier
Entity Not Found
No Matching Results
Ambiguous Result
Permission Denied
Entity Unavailable
Context Expired
Integration Failure
```

The Apple-facing layer should translate internal failures into appropriate system-level results without exposing unnecessary implementation details.

## 24. Testing

Important test categories include:

```text
Identifier Resolution
Search Resolution
Contextual Resolution
Privacy Filtering
Authorization
Ambiguity
Deleted Entities
Unavailable Entities
Large Result Sets
Failure Handling
```

Testing should distinguish query failure from canonical entity failure.

## 25. Implementation Principle

```text
Apple System
      ↓
EntityQuery
      ↓
Thin Apple Adapter
      ↓
Context Founder
      ↓
Privacy / Policy
      ↓
Canonical Entity Resolver
      ↓
iRiel Entity
      ↓
AppEntity Projection
```

## 26. Architectural Objective

The objective of `EntityQuery` is to provide Apple with a controlled, contextual, privacy-aware mechanism for resolving iRiel entities.

`EntityQuery` is therefore the **resolution bridge between Apple's entity system and the canonical iRiel domain model**.

**Apple asks for the entity. Context finds the meaning. iRiel owns the entity.**
