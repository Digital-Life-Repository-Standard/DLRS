# Architecture

```mermaid
flowchart LR
  A[Participant] --> B[humans/ record]
  B --> C[Schema Validation]
  C --> D[Human Review]
  D --> E[Registry]
  B --> F[Object Storage Pointers]
  F --> G[Build Pipeline]
  G --> H[Runtime]
  H --> I[Public Output Labeling]
  I --> J[Audit & Takedown]
```

## Detailed Diagrams

- [Repository Structure](diagrams/repository-structure.md) — directory layout for records, schemas, and tools
- [Data Flow](diagrams/data-flow.md) — authoring pipeline and 5-stage runtime assembly
- [Consent & Withdrawal](diagrams/consent-withdrawal.md) — consent evidence requirements and withdrawal lifecycle
- [Privacy Boundaries](diagrams/privacy-boundaries.md) — sensitivity levels and storage boundaries
