---
appliesTo:
  - type: capability
    id: delete-idle-conversions
    contexts:
      - place: desktop::app-settings
references:
  - kind: code
    role: implementation
    target: src/domain/pending-cleanup.ts#idleDays
  - kind: adr
    role: intent
    target: docs/adr/0061-the-processing-tab-shows-what-waits-and-cleans-up-what-has-waited-long.md
---

# The clean-up deletes whole conversions untouched for 7, 30 or 90 days

The clean-up of the Processing tab counts what it would delete before it asks, and deletes only conversions nothing has changed in for longer than the days chosen, whole, unsaved books included.
