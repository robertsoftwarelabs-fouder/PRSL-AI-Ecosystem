# PRSL-AI App Intents Architecture

## 1. Purpose

App Intents is the primary Apple integration mechanism through which PRSL-AI can expose selected @iRiel capabilities to system-level experiences.

Within the PRSL-AI architecture, App Intents functions as an **integration contract between the Apple ecosystem and the iRiel capability layer**.

The architectural relationship is:

```text
Human
  ↓
Apple System
  ↓
App Intent
  ↓
Apple Integration Layer
  ↓
@iRiel
  ↓
iRiel Core
  ↓
Context + Identity + Policy
  ↓
Capability
  ↓
Action
```

App Intents should expose capabilities without becoming the owner of the underlying intelligence architecture.

---

## 2. Architectural Position

App Intents belongs to the Apple Integration Layer.

```text
PRSL-AI
   │
   ├── Core Architecture
   │      ├── Identity
   │      ├── Context
   │      ├── Memory
   │      ├── Orchestration
   │      ├── Router
   │      └── Policy
   │
   └── Apple Integration
          └── App Intents
```

This separation prevents Apple-specific implementation details from becoming embedded throughout the iRiel Core.

---

## 3. App Intent as an Adapter

An App Intent should be treated as an adapter.

```text
Apple Request
      ↓
App Intent
      ↓
Integration Adapter
      ↓
iRiel Capability
```

The App Intent should translate Apple system requests into canonical iRiel operations.

The preferred architectural principle is:

```text
Thin Apple Layer
       ↓
Stable iRiel Domain
```

---

## 4. Intent Definition

An App Intent represents an operation that can be exposed to the Apple system.

Conceptually:

```text
App Intent
   │
   ├── Title
   ├── Description
   ├── Parameters
   ├── Entities
   ├── Validation
   └── Perform Operation
```

The implementation should delegate actual domain behavior to the appropriate iRiel capability.

---

## 5. Intent Execution

A typical execution flow is:

```text
System Invocation
      ↓
App Intent
      ↓
Parameter Resolution
      ↓
Entity Resolution
      ↓
Context Resolution
      ↓
Privacy / Policy Check
      ↓
iRiel Core
      ↓
Capability
      ↓
Action
      ↓
Intent Result
      ↓
Apple System
```

This ensures that system-level invocation still passes through the same architectural controls used by other interfaces.

---

## 6. Parameters

Intent parameters represent information required to execute an operation.

Parameters may represent:

```text
Text
Numbers
Dates
Entities
Enums
Booleans
Configuration
User Selections
```

Parameters should remain focused on the operation being exposed.

They should not become a duplicate of the complete iRiel context model.

---

## 7. Entity Parameters

When an operation references an identifiable object, App Intents may use entity representations.

```text
User Input
    ↓
Entity Parameter
    ↓
Entity Resolution
    ↓
iRiel Domain Entity
```

Examples include:

```text
Document
Task
Person
Project
Device
Application
Service
```

The Apple representation should remain a projection of the canonical iRiel entity.

---

## 8. Entity Resolution

The resolution boundary is:

```text
Apple Entity
      ↓
Identifier
      ↓
App Intent
      ↓
Apple Adapter
      ↓
iRiel Entity
      ↓
Context Founder
      ↓
Policy
```

This allows App Intents to work with Apple's entity model without making Apple the source of truth for iRiel entities.

---

## 9. Context Integration

App Intents may receive information from the Apple system, but contextual interpretation belongs to PRSL-AI.

```text
App Intent
    ↓
System Context
    ↓
Context Founder
    ↓
Unified Context
    ↓
Intent Resolution
```

This enables requests to be interpreted according to the broader state of the interaction.

For example:

```text
"Open it"
```

should not necessarily be treated as an isolated command.

The relevant entity may be resolved through the active contextual state.

---

## 10. Policy Boundary

Every App Intent invocation must respect PRSL-AI policy.

```text
App Intent
     ↓
Requested Operation
     ↓
Policy Evaluation
     ↓
Authorization
     ↓
Capability Execution
```

The existence of an App Intent does not automatically authorize access to private context or sensitive capabilities.

---

## 11. Privacy

App Intents must follow the PRSL-AI principle:

```text
Context Availability
        ≠
Context Authorization
```

An intent should receive only the information required for its authorized operation.

```text
Available Context
       ↓
Privacy Policy
       ↓
Minimum Necessary Context
       ↓
App Intent
```

This prevents system integration surfaces from becoming unrestricted access paths into personal intelligence data.

---

## 12. App Shortcuts

Selected App Intents may be exposed through App Shortcuts and other Apple discovery mechanisms.

Conceptually:

```text
iRiel Capability
      ↓
App Intent
      ↓
App Shortcut
      ↓
Apple System
      ↓
User
```

Not every internal capability should automatically become a user-facing shortcut.

Exposure should be intentional and policy-controlled.

---

## 13. Siri Integration

App Intents provide an important bridge to Siri.

```text
Human
  ↓
Siri
  ↓
App Intent
  ↓
iRiel Integration
  ↓
iRiel Core
```

Siri remains an interaction surface.

App Intents provide the integration contract.

@iRiel remains responsible for the underlying contextual intelligence.

---

## 14. Spotlight Integration

App Intents may also participate in Apple system discovery and Spotlight-related experiences.

```text
iRiel Entity / Capability
        ↓
App Intent / Entity Definition
        ↓
Apple Indexing
        ↓
Spotlight
        ↓
System Interaction
```

The purpose is to make relevant capabilities discoverable without moving the canonical domain model into the Apple platform.

---

## 15. App Intent Results

The result of an intent should contain the information necessary for the Apple system to continue the interaction.

Conceptually:

```text
Capability Result
      ↓
Intent Result
      ↓
Apple Representation
      ↓
System Experience
```

The result should not expose internal architectural state unnecessarily.

---

## 16. Error Handling

Errors should be translated at the integration boundary.

```text
iRiel Error
    ↓
Integration Layer
    ↓
App Intent Error Representation
    ↓
Apple System
```

Internal implementation details should not leak into the user-facing system experience.

Errors should remain:

* understandable;
* actionable;
* privacy-aware;
* consistent with the capability contract.

---

## 17. Authorization and Sensitive Operations

Sensitive operations may require additional authorization.

```text
Intent
  ↓
Sensitivity Evaluation
  ↓
Authorization Required?
  │
  ├── No → Execute
  │
  └── Yes
       ↓
   Authorization
       ↓
     Execute
```

App Intents must not circumvent Apple security mechanisms or PRSL-AI privacy policies.

---

## 18. AI-Agnostic Execution

An App Intent does not determine which intelligence provider executes the underlying operation.

After invocation:

```text
App Intent
     ↓
iRiel Core
     ↓
Router
     ↓
┌─────────────────────┐
│ On-Device           │
│ Local Model         │
│ Apple Intelligence  │
│ OpenAI              │
│ Anthropic           │
│ Google              │
│ MCP                 │
│ API                 │
│ Tool                │
└─────────────────────┘
```

Therefore:

```text
App Intent
    ≠
AI Provider
```

The integration surface remains independent from the intelligence provider.

---

## 19. Platform Isolation

Apple-specific types and implementation details should remain isolated whenever practical.

```text
Apple Frameworks
      ↓
Apple Integration Layer
      ↓
Canonical iRiel Interface
      ↓
Domain Capability
```

This allows the same capability to be accessed through:

```text
Siri
AppWeb
API
MCP
Web
Other Platforms
```

without requiring the capability itself to become Apple-specific.

---

## 20. Testing Boundary

App Intent testing should validate both the Apple integration contract and the underlying iRiel capability.

```text
App Intent Test
      ↓
Parameter Resolution
      ↓
Entity Resolution
      ↓
Policy
      ↓
Capability
      ↓
Result
```

Testing should distinguish between:

```text
Integration Failure
```

and:

```text
Domain Capability Failure
```

This makes debugging and architectural validation more precise.

---

## 21. Architectural Independence

App Intents are replaceable integration mechanisms.

```text
                 iRiel Core
                     │
       ┌─────────────┼─────────────┐
       ▼             ▼             ▼
   Apple Layer    Web Layer     API Layer
       │
   App Intents
```

The removal or replacement of App Intents must not invalidate the underlying iRiel capability architecture.

---

## 22. Implementation Principle

The preferred implementation model is:

```text
Apple System
      ↓
App Intent
      ↓
Thin Adapter
      ↓
Canonical iRiel Interface
      ↓
Policy
      ↓
Context
      ↓
Capability
```

Business logic, memory management, contextual intelligence, and provider selection should remain outside the App Intent whenever practical.

---

## 23. Architectural Objective

App Intents establish a controlled bridge between Apple system intelligence and the PRSL-AI ecosystem.

The target architecture is:

```text
Human
  ↓
Apple System
  ↓
App Intent
  ↓
Apple Integration Layer
  ↓
@iRiel
  ↓
Identity
  +
Context
  +
Memory
  +
Policy
  ↓
Orchestration
  ↓
Router
  ↓
Capability
  ↓
Action
  ↓
Adaptive Feedback
  ↓
Human
```

App Intents therefore function as **Apple-native capability contracts**, while @iRiel remains the canonical personal intelligence environment.

**Apple invokes the capability. iRiel owns the intelligence behind it.**
