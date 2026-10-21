---
availability:
  - place: desktop
domain: ready-books
references:
  - kind: code
    role: implementation
    target: src/renderer/workflow-app.tsx#WorkflowApp
  - kind: code
    role: implementation
    target: src/main/ipc/pending.ts#registerPendingHandlers
  - kind: code
    role: implementation
    target: src/adapters/library/fs-pending-runs.ts#FsPendingRuns
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/exporting.mdx
  - kind: adr
    role: intent
    target: docs/adr/0026-process-then-save-pending-books.md
---

# View books

Opens the results of an earlier pending conversion from Ready books on the queue, to save, open or share its books.
