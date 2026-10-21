---
availability:
  - place: desktop
domain: ready-books
references:
  - kind: code
    role: implementation
    target: src/main/ipc/pending-decisions.ts#discardRefusal
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

# Delete pending books

Permanently deletes every pending book of one conversion, after a question. Copies saved elsewhere and the original manga stay.
