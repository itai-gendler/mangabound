---
availability:
  - place: desktop
domain: queue
references:
  - kind: code
    role: implementation
    target: src/renderer/workflow-app.tsx#WorkflowApp
  - kind: code
    role: implementation
    target: src/application/workflows/single-run.ts#SingleInputRun
  - kind: code
    role: implementation
    target: src/application/workflows/library-run.ts#LibraryRun
  - kind: code
    role: implementation
    target: src/application/workflows/book-production.ts#BookProduction
  - kind: code
    role: implementation
    target: src/domain/run-report.ts#finishRunReport
  - kind: code
    role: implementation
    target: src/main/ipc/run-job.ts#runJob
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/processing.mdx
  - kind: adr
    role: intent
    target: docs/adr/0009-process-modes.md
  - kind: adr
    role: intent
    target: docs/adr/0027-bounded-volume-conversion.md
---

# Process the queue

Runs the chosen steps for every item that is ready, one item after another: mangabind joins each item's chapters into volume files, and mangapress converts them into books for the chosen device and format. The books of one press of Process are one pending conversion, shown in the results and kept under Ready books until they are saved or deleted. Items that are not ready are left out and reported, and a failed item stays in the queue.
