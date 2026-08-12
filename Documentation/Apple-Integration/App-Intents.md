# PRSL-AI App Intents Architecture

## Purpose

App Intents is the Apple integration mechanism through which PRSL-AI exposes selected @iRiel capabilities to Apple system experiences.

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

App Intents are integration contracts, not owners of the underlying intelligence architecture.

## Architectural Principles

- App Intents remain thin adapters.
- Canonical domain behavior remains in iRiel Core and capabilities.
- Entity resolution maps Apple representations back to canonical iRiel entities.
- Every invocation passes through context, privacy, and authorization policy.
- App Intent exposure does not imply authorization.
- Provider selection remains AI-agnostic.

## Execution Pipeline

```text
System Invocation
      ↓
App Intent
      ↓
Parameter / Entity Resolution
      ↓
Context Resolution
      ↓
Privacy / Policy
      ↓
iRiel Core
      ↓
Capability
      ↓
Intent Result
      ↓
Apple System
```

## AI Independence

```text
App Intent
     ↓
iRiel Core
     ↓
Router
     ↓
Selected Intelligence
```

The selected intelligence may be on-device, local, Apple Intelligence, OpenAI, Anthropic, Google, MCP, an API, or another supported capability.

## Architectural Objective

App Intents provide Apple-native capability contracts while @iRiel remains the canonical personal intelligence environment.

**Apple invokes the capability. iRiel owns the intelligence behind it.**
