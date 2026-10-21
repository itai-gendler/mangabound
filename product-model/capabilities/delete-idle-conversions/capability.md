---
availability:
  - place: desktop
domain: processing
references:
  - kind: code
    role: implementation
    target: src/main/ipc/pending-cleanup.ts#registerPendingCleanupHandlers
  - kind: code
    role: implementation
    target: src/domain/pending-cleanup.ts#idleDays
  - kind: adr
    role: intent
    target: docs/adr/0061-the-processing-tab-shows-what-waits-and-cleans-up-what-has-waited-long.md
---

# Delete what has waited

Deletes, after a question, every pending conversion nothing has changed in for more than 7, 30 or 90 days, whole, from Books waiting to be saved in the Processing tab.
