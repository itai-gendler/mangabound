---
appliesTo:
  - type: capability-scenario
    id: confirm-a-library-title
  - type: capability-scenario
    id: edited-volumes-cannot-be-kept
  - type: capability-scenario
    id: make-the-books-of-a-folder
references:
  - kind: code
    role: implementation
    target: src/adapters/mangabind/binding-port.ts#MangabindBindingAdapter
  - kind: code
    role: implementation
    target: src/adapters/mangabind/stored-details.ts#carryStoredDetails
  - kind: adr
    role: intent
    target: docs/adr/0008-mapping-starts-from-mangabind-grouping.md
---

# A changed grouping is kept in the manga folder's mangabind.json

A grouping that differs from the one mangabind proposed is written into the manga folder's mangabind.json: for a library title when its mapping is confirmed, for a manga folder when the run joins it. The file's other keys, the author and language included, are kept. A grouping accepted unchanged writes nothing. When the file cannot be written, that item fails before anything is joined and stays in the queue.
