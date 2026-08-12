# Apple Integration

The Apple Integration Layer documents how PRSL-AI participates in Apple system experiences without making Apple the owner of the canonical architecture.

## Components

```text
Apple-Integration/
├── Apple-Intelligence.md
├── Siri.md
├── App-Intents.md
├── AppEntity.md
├── EntityQuery.md
├── IndexedEntity.md
├── Spotlight.md
├── App-Schemas.md
├── Contextual-UI.md
└── README.md
```

## Boundary

```text
┌──────────────────────────────┐
│          PRSL-AI Core        │
│ Identity / Context / Memory  │
│ Orchestration / Router       │
│ Privacy / Accessibility      │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│   Apple Integration Layer    │
│ Intents / Entities / Schema  │
│ Spotlight / Siri / UI        │
└──────────────┬───────────────┘
               │
               ▼
        Apple System Services
```

## Principles

1. Canonical domain independence.
2. AI-provider independence.
3. Privacy and authorization before exposure.
4. Contextual continuity.
5. Human-centered interaction.
6. Thin Apple-specific adapters.
7. Failure isolation between Apple integration and the iRiel core.

## Status

These documents describe the target architectural model. A documented capability is not evidence of implementation. Implementation status must be verified against repository evidence.
