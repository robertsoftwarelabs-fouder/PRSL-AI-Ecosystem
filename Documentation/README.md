# PRSL-AI Documentation

This directory contains canonical PRSL-AI architectural and domain documentation.

```text
Documentation/
├── Architecture-Documentation/
├── Domain-Documentation/
├── Apple-Integration/
└── README.md
```

## Documentation Philosophy

PRSL-AI distinguishes between:

```text
Concept
   ↓
Architecture
   ↓
Design
   ↓
Implementation
   ↓
Validation
```

Documentation describes architectural intent and decisions. It does not by itself prove implementation.

## Apple Integration

Apple-specific integration is isolated under `Apple-Integration/` so Apple APIs do not become the owner of the canonical PRSL-AI domain, context, memory, policy, or intelligence architecture.

## Research

Research is maintained separately under `Research/` and provides evidence for architectural evolution.
