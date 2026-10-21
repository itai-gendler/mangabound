---
appliesTo:
  - type: capability-scenario
    id: make-the-books-of-a-folder
  - type: capability-scenario
    id: run-a-failed-title-again
  - type: capability-scenario
    id: an-item-fails
  - type: capability-scenario
    id: a-library-title-fails
references:
  - kind: code
    role: implementation
    target: src/domain/run-report.ts#finishRunReport
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#isPendingTitle
---

# An item leaves the queue once its books are made

After a run, an item that made its books leaves the queue; one that failed stays, to be fixed and run again. A library stays until every one of its titles is saved, and the next run makes only the titles still to make.
