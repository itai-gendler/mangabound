---
availability:
  - place: desktop
domain: queue
references:
  - kind: code
    role: implementation
    target: src/adapters/input/classify-input-paths.ts#classifyInputPaths
  - kind: code
    role: implementation
    target: src/application/workflows/input-sessions.ts#InputSessions
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#queueReducer
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/adding-manga.mdx
  - kind: adr
    role: intent
    target: docs/adr/0012-libraries-in-the-queue.md
---

# Add items to the queue

Folders and CBZ files go into the queue from Files, Folder, a click on the drop area or a drop, and each one is read before a run can use it: a manga folder for its chapters and the volumes their names declare, a library for the manga folders in it, a CBZ as one complete volume.
