---
appliesTo:
  - type: capability
    id: process-queue
  - type: capability
    id: choose-working-folder
references:
  - kind: code
    role: implementation
    target: src/domain/working-space.ts#lowSpace
  - kind: adr
    role: intent
    target: docs/adr/0060-the-queue-warns-of-too-little-room-before-processing.md
---

# The queue warns when the working drives may be short of room

Before Process, the queue estimates about a megabyte a page in each place the app works and warns, above the button, when a drive has less than that or under 1 GB. It is only a warning: Process still works, and CBZ files are not counted because their pages are unknown until opened.
