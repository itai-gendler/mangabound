---
availability:
  - place: desktop
references:
  - kind: code
    role: implementation
    target: src/main/quit-cleanup.ts#cleanUpBeforeQuit
  - kind: code
    role: implementation
    target: src/main/leaving.ts#LeavingGuard
  - kind: adr
    role: intent
    target: docs/adr/0059-closing-the-app-during-a-conversion-asks-first.md
  - kind: adr
    role: intent
    target: docs/adr/0026-process-then-save-pending-books.md
---

# Close Mangabound

Ends the app: sharing stops, and the pending conversions whose every book was saved are removed. While a conversion runs, closing asks first.
