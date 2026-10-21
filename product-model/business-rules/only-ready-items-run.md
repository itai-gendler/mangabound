---
appliesTo:
  - type: capability
    id: process-queue
  - type: capability
    id: validate-plan
references:
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#runnableRows
  - kind: code
    role: implementation
    target: src/domain/run-report.ts#finishRunReport
  - kind: adr
    role: intent
    target: docs/adr/0010-input-queue.md
---

# A run takes only the items that are ready

Process and Validate plan wait until every item has been read. An item that could not be read, has no chapters, still needs volumes, or has chapters without a volume that were not accepted in the editor, is left out of the run and reported with the reason, and a folder that needs volumes is offered Fix. A library runs only its grouped titles that are not saved yet.
