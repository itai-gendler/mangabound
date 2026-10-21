---
appliesTo:
  - type: capability-scenario
    id: add-a-library
  - type: capability-scenario
    id: make-the-books-of-a-library
  - type: capability
    id: skip-grouping
references:
  - kind: code
    role: implementation
    target: src/domain/process-mode.ts#resolveMode
  - kind: adr
    role: intent
    target: docs/adr/0012-libraries-in-the-queue.md
---

# A library is always grouped title by title

A library is joined by mangabind title by title before anything else, so it can group only, or group and convert. With grouping turned off it is left out of the run with that reason rather than grouped anyway.
