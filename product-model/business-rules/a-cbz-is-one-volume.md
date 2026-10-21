---
appliesTo:
  - type: capability-scenario
    id: add-a-cbz
  - type: capability-scenario
    id: convert-a-cbz
  - type: capability-scenario
    id: only-join-volumes
references:
  - kind: code
    role: implementation
    target: src/domain/process-mode.ts#unsupportedModeReason
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#rowMode
---

# A CBZ in the queue is one complete volume

A CBZ is never grouped: it goes straight to the e-reader step as one book, and a run that only groups chapters has nothing to join in it and leaves it out with that reason.
