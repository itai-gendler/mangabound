---
availability:
  - place: desktop
references:
  - kind: code
    role: implementation
    target: src/main/diagnostics.ts#diagnosticsText
  - kind: code
    role: implementation
    target: src/main/ipc/troubleshooting.ts#registerTroubleshootingHandlers
  - kind: adr
    role: intent
    target: docs/adr/0057-the-about-tab-helps-report-a-problem.md
---

# Copy diagnostics

Puts a short report for a problem on the clipboard from the About tab: versions, system, processors and memory, the window language, whether a working folder was chosen, and whether the conversion tools passed their check.
