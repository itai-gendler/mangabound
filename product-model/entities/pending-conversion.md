---
domain: ready-books
relations:
  - entity: ready-book
    verb: holds
    cardinality: one-to-many
references:
  - kind: code
    role: implementation
    target: src/adapters/library/fs-pending-runs.ts#FsPendingRuns
  - kind: code
    role: implementation
    target: src/main/ipc/pending.ts#registerPendingHandlers
  - kind: adr
    role: intent
    target: docs/adr/0026-process-then-save-pending-books.md
---

# Pending conversion

The books of one press of Process, kept on this computer, in the app's own data or in the Pending folder of the working folder, until they are saved or deleted. Earlier ones are listed under Ready books on the queue and survive a restart.

## Information kept

- **Made at** — when the run that made it began
- **Books** — its ready books, and how many
- **Size** — how much room its books take
- **Item results** — what each item of its run came to: books made, could not be converted, or left out, with the reason; shown with the results of that run only
