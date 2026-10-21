---
appliesTo:
  - type: capability
    id: choose-working-folder
  - type: capability
    id: use-default-working-folder
references:
  - kind: code
    role: implementation
    target: src/main/ipc/processing-folder.ts#registerProcessingFolderHandlers
  - kind: adr
    role: intent
    target: docs/adr/0056-the-app-works-in-a-folder-a-person-can-choose.md
---

# The working folder changes only while nothing converts or is shared

Choosing a working folder, or going back to the default one, is refused while a conversion runs or sharing is on, so nothing is moved from under them. A chosen folder whose drive is not connected stops conversions rather than letting them work somewhere else.
