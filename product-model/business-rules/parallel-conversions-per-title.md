---
appliesTo:
  - type: capability
    id: process-queue
  - type: capability
    id: change-processing-settings
  - type: entity
    id: app-settings
    facts:
      - Parallel conversions
references:
  - kind: code
    role: implementation
    target: src/application/workflows/conversion-concurrency.ts#conversionsAtOnce
  - kind: adr
    role: intent
    target: docs/adr/0068-how-many-are-converted-at-once-is-a-choice-a-queue-keeps.md
---

# Items run one after another; the books of one title run up to Parallel conversions at once

Automatic converts one book for every 4 processors or every 4 GiB of memory, whichever is fewer, at least 1 and at most 3. A chosen number may be higher, up to one for every 2 processor threads or 2 GiB of memory, and never above 12; a number kept on a bigger computer is lowered to what this one can be asked for. A queue keeps the choice it began with.
