---
appliesTo:
  - type: capability
    id: copy-diagnostics
    contexts:
      - place: desktop::app-settings
references:
  - kind: code
    role: implementation
    target: src/main/diagnostics.ts#diagnosticsText
  - kind: adr
    role: intent
    target: docs/adr/0057-the-about-tab-helps-report-a-problem.md
---

# Diagnostics hold no path and no name

What Copy diagnostics puts on the clipboard says whether a working folder was chosen but not which, and names no book or folder.
