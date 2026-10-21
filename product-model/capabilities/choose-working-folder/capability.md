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

# Choose a working folder

Moves where Mangabound builds volumes and keeps finished books to a folder the User picks, with Choose a folder… in the Processing tab. Pending and Scratch are made inside it, and the next conversion uses it.
