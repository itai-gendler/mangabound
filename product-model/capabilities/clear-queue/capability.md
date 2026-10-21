---
availability:
  - place: desktop
domain: queue
references:
  - kind: code
    role: implementation
    target: src/renderer/workflow-app.tsx#WorkflowApp
---

# Clear the queue

Takes every item out of the queue at once. No file on disk is touched, and the ready books of earlier runs stay.
