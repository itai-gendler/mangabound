---
availability:
  - place: desktop
domain: queue
references:
  - kind: code
    role: implementation
    target: src/application/workflows/single-run.ts#SingleInputRun
  - kind: code
    role: implementation
    target: src/renderer/workflow-app.tsx#WorkflowApp
  - kind: adr
    role: intent
    target: docs/adr/0010-input-queue.md
---

# Validate plan

Shows what a run of the queue would make without making anything: for each item that is ready, the books with their names and page counts, from the same checks a run makes before it starts.
