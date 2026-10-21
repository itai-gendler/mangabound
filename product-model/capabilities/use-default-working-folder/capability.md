---
availability:
  - place: desktop
domain: processing
references:
  - kind: code
    role: implementation
    target: src/main/ipc/processing-folder.ts#registerProcessingFolderHandlers
  - kind: code
    role: implementation
    target: src/domain/app-settings.ts#choosingFolder
  - kind: code
    role: implementation
    target: src/adapters/library/processing-folders.ts
  - kind: adr
    role: intent
    target: docs/adr/0056-the-app-works-in-a-folder-a-person-can-choose.md
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/exporting.mdx
---

# Use the default folder

Puts the working places back where Mangabound picks them: the system's temporary folder for volumes and the app's own data for finished books.
