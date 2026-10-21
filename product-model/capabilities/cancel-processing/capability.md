---
availability:
  - place: desktop
domain: queue
references:
  - kind: code
    role: implementation
    target: src/main/ipc/conversion.ts#registerConversionHandlers
  - kind: code
    role: implementation
    target: src/domain/run-report.ts#finishRunReport
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/processing.mdx
---

# Cancel conversion

Stops a run in progress. Books already made stay ready, and the source manga is never touched.
