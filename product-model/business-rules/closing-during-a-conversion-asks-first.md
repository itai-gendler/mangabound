---
appliesTo:
  - type: capability
    id: close-mangabound
  - type: capability
    id: process-queue
references:
  - kind: code
    role: implementation
    target: src/main/leaving.ts#LeavingGuard
  - kind: adr
    role: intent
    target: docs/adr/0059-closing-the-app-during-a-conversion-asks-first.md
---

# Closing Mangabound while a conversion runs asks first

From the press of Process to the last item, leaving the app asks once whether to close, with Keep converting as the safe answer; closing anyway stops the conversion, and the book being made is lost.
