---
availability:
  - place: desktop
domain: updates
references:
  - kind: code
    role: implementation
    target: src/domain/update-check.ts#chooseUpdate
  - kind: code
    role: implementation
    target: src/application/workflows/update-check.ts#UpdateCheckWorkflow
  - kind: adr
    role: intent
    target: docs/adr/0063-the-app-looks-for-a-newer-version-when-asked.md
---

# Check for updates

Asks GitHub, only when the User clicks, whether a newer release than the installed one is out, pre-releases included.
