# PRSL-AI Spotlight Integration Architecture

## 1. Purpose

Spotlight provides a system-level discovery surface through which users can find relevant information, entities, and actions across Apple platforms.

Within PRSL-AI, Spotlight is treated as an **integration and discovery surface**, not as the canonical source of iRiel information.

```text
Human
  ↓
Spotlight
  ↓
Indexed iRiel Representation
  ↓
Entity / Intent Resolution
  ↓
PRSL-AI
  ↓
Context + Policy
  ↓
Action
```

## 2. Architectural Position

Spotlight belongs to the Apple Integration Layer.

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
          ├── Spotlight
          ├── IndexedEntity
          ├── AppEntity
          ├── EntityQuery
          └── App Intents
```

Spotlight should remain replaceable without affecting the canonical iRiel architecture.

## 3. Discovery Model

```text
Human Query
      ↓
Spotlight
      ↓
Indexed Representation
      ↓
Relevant Entity / Action
      ↓
Resolution
      ↓
iRiel Context
      ↓
Capability
      ↓
Action
```

Spotlight provides discovery. iRiel provides meaning and execution.

## 4. Spotlight as a Projection Surface

```text
Canonical iRiel Entity
        ↓
Privacy / Exposure Policy
        ↓
Apple Projection
        ↓
Spotlight
```

The indexed representation should contain only information required for useful discovery.

## 5. Searchable Information

Potentially discoverable iRiel information may include:

```text
Entities
Documents
Projects
Tasks
Capabilities
Actions
Relevant Application Content
```

Actual exposure depends on entity type, authorization, privacy policy, and Apple platform capabilities.

## 6. Privacy Boundary

```text
Available Internally
       ≠
Searchable System-Wide
```

```text
Canonical Data
      ↓
Privacy Policy
      ↓
Eligibility
      ↓
Projection
      ↓
Spotlight
```

Privacy restrictions must be evaluated before indexing.

## 7. Minimum Necessary Exposure

Spotlight should receive only the information required to identify the result, provide useful discovery, disambiguate the entity, and support an authorized action.

Private metadata should not be indexed by default.

## 8. Spotlight and IndexedEntity

```text
iRiel Entity
     ↓
IndexedEntity
     ↓
Spotlight
```

Spotlight consumes a controlled representation rather than accessing the canonical iRiel data model directly.

## 9. Spotlight and AppEntity

```text
Spotlight
   ↓
Indexed Representation
   ↓
AppEntity
   ↓
Entity Resolution
   ↓
iRiel Entity
```

## 10. Spotlight and EntityQuery

```text
Spotlight
    ↓
Indexed Entity
    ↓
Identifier
    ↓
EntityQuery
    ↓
AppEntity
    ↓
Canonical iRiel Entity
```

## 11. Spotlight and App Intents

```text
Human
  ↓
Spotlight
  ↓
Entity / Action
  ↓
App Intent
  ↓
iRiel Capability
  ↓
Action
```

## 12. Contextual Discovery

```text
Search Query
      +
Current Context
      +
Entity Relevance
      ↓
Candidate Results
      ↓
Relevant iRiel Entity
```

Context may improve relevance, but it must not override explicit user intent or privacy policies.

## 13. Contextual Continuity

```text
Spotlight
    ↓
Selected Entity
    ↓
Identifier
    ↓
Context Founder
    ↓
Current Context
    ↓
@iRiel
    ↓
Capability
```

## 14. Spotlight and Memory

```text
Memory
   ↓
Privacy / Exposure Policy
   ↓
Eligibility Evaluation
   ↓
Optional Projection
   ↓
Spotlight
```

```text
Memory
  ≠
Spotlight Index
```

Especially sensitive or intimate memory should remain outside system-wide discovery unless explicitly authorized.

## 15. Spotlight and Context Founder

Context Founder remains the canonical owner of contextual intelligence.

```text
Spotlight
     ↓
Entity / Action Reference
     ↓
Context Founder
     ↓
Relevant Context
     ↓
iRiel Resolution
```

## 16. Spotlight and iRiel Resonance

```text
Human
  ↕
Spotlight
  ↕
Entity
  ↕
Context
  ↕
@iRiel
  ↕
Capability
  ↕
Action
```

## 17. Index Lifecycle

```text
Entity Created
      ↓
Eligibility
      ↓
Projection
      ↓
Index
      ↓
Discoverable
      ↓
Entity Updated
      ↓
Reindex
      ↓
Entity Removed / Restricted
      ↓
Index Removal
```

## 18. Index Invalidation

Potential invalidation conditions include entity deletion, rename, state change, permission revocation, privacy-policy change, loss of relevance, or application state changes.

The goal is to prevent stale or unauthorized information from remaining discoverable.

## 19. Security Model

Spotlight integration should consider:

```text
Authorization
Privacy
Data Minimization
Identifier Integrity
Index Staleness
Revocation
Entity Availability
```

System discovery must never become an unintended data-exfiltration path.

## 20. AI-Agnostic Architecture

```text
Spotlight
    ↓
iRiel Entity / Intent
    ↓
iRiel Core
    ↓
Router
    ↓
Capability
    ↓
Selected Intelligence Provider
```

Spotlight remains independent of the AI runtime.

## 21. Platform Independence

```text
                iRiel Entity
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
    Spotlight       Siri         MCP
        │
     Apple
   Projection
```

Apple integration is an adapter layer, not the domain architecture.

## 22. Performance

```text
Fast Index Updates
Bounded Indexed Data
Stable Identifiers
Efficient Resolution
Incremental Updates
Graceful Failure
```

Complex reasoning should occur after the system has resolved the relevant entity or action into the iRiel architecture.

## 23. Failure Handling

```text
Indexing Failure
Stale Result
Entity Not Found
Invalid Identifier
Permission Denied
Entity Unavailable
App Integration Failure
```

```text
Spotlight Failure
      ≠
iRiel Domain Failure
```

## 24. Testing

```text
Index Creation
Search Discovery
Entity Selection
Entity Resolution
App Intent Invocation
Privacy Filtering
Permission Changes
Index Removal
Stale Data
Contextual Resolution
Failure Recovery
```

## 25. Implementation Principle

```text
Canonical iRiel Entity
        ↓
Eligibility
        ↓
Privacy / Policy
        ↓
Apple Projection
        ↓
Spotlight
        ↓
Discovery
        ↓
EntityQuery / App Intent
        ↓
AppEntity
        ↓
Canonical Entity
        ↓
Context Founder
        ↓
iRiel Capability
        ↓
Action
```

## 26. Architectural Objective

The objective of Spotlight integration is to make authorized iRiel entities and capabilities discoverable through Apple's system search while maintaining privacy, contextual continuity, domain ownership, and AI-provider independence.

**Spotlight provides discovery. iRiel provides identity, context, intelligence, and action.**
