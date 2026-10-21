---
availability:
  - place: desktop
domain: ready-books
references:
  - kind: code
    role: implementation
    target: src/library/pending-save.ts#saveWithUniqueName
  - kind: code
    role: implementation
    target: src/library/unique-name.ts#uniqueFileName
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

# Save all to folder

Copies every ready book of one conversion into a folder the User picks, never replacing a file already there.
