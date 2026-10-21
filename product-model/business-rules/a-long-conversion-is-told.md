---
appliesTo:
  - type: capability-scenario
    id: a-long-conversion-ends-unseen
  - type: capability
    id: change-processing-settings
references:
  - kind: code
    role: implementation
    target: src/domain/queue-run.ts#shouldNotify
  - kind: adr
    role: intent
    target: docs/adr/0065-a-queue-is-a-signal-the-window-gives-the-main-process.md
---

# The end of a long conversion is told only when nobody is looking

A system notification says how a queue ended only when Tell me when a long conversion ends is on, the queue took more than 30 seconds, and no Mangabound window is in front; never for a queue the person stopped. While a queue runs, from the press of Process to its last item, the computer is kept from sleeping if Keep the computer awake while converting is on, and closing the app asks first.
