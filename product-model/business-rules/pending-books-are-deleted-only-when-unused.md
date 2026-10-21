---
appliesTo:
  - type: capability
    id: delete-pending-conversion
  - type: capability
    id: delete-idle-conversions
references:
  - kind: code
    role: implementation
    target: src/main/ipc/pending-decisions.ts#discardRefusal
  - kind: adr
    role: intent
    target: docs/adr/0026-process-then-save-pending-books.md
---

# Pending books are not deleted while they are shared, saved from or converted into

A pending conversion cannot be deleted while the ready books are shared, since every pending conversion is in what is served, nor while any conversion runs, nor while its own books are being saved. Deleting never touches the original manga or copies saved elsewhere.
