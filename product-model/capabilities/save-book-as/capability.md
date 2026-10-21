---
availability:
  - place: desktop
domain: ready-books
references:
  - kind: code
    role: implementation
    target: src/main/ipc/pending-decisions.ts#wrongExtension
  - kind: code
    role: implementation
    target: src/application/workflows/library-publisher.ts#LibraryPublisher
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

# Save as

Saves a copy of one ready book under the name and in the folder the User picks in the system's save dialog, and records it in that folder's catalog. The pending copy stays.
