---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/renderer/workflow-app.tsx#WorkflowApp
  - kind: code
    role: implementation
    target: src/domain/process-mode.ts#modeFromSteps
  - kind: adr
    role: intent
    target: docs/adr/0009-process-modes.md
---

# Skip grouping

Sends a manga folder to mangapress as one book, without grouping its chapters, by turning off the queue's Group chapters into volumes step.
