---
appliesTo:
  - type: capability
    id: share-ready-books
  - type: capability-scenario
    id: list-recently-converted-books
references:
  - kind: code
    role: implementation
    target: src/main/ipc/sharing-target.ts#sharingTarget
  - kind: code
    role: implementation
    target: src/adapters/library/pending-catalog-store.ts
---

# Sharing the ready books shares all of them

Share these books serves the ready books of every pending conversion, old ones never saved or deleted included, and a book converted while sharing is on shows up on the reader too.
