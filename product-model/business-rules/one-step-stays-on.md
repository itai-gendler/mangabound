---
appliesTo:
  - type: capability
    id: change-conversion-options
  - type: capability
    id: skip-grouping
references:
  - kind: code
    role: implementation
    target: src/domain/process-mode.ts#modeFromSteps
  - kind: adr
    role: intent
    target: docs/adr/0009-process-modes.md
---

# At least one process step stays on

Group chapters into volumes and Convert for e-reader can each be turned off, never both: a run always groups, converts, or does both.
