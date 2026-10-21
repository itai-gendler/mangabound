---
availability:
  - place: desktop
domain: processing
references:
  - kind: code
    role: implementation
    target: src/renderer/components/settings/processing-tab.tsx
  - kind: code
    role: implementation
    target: src/application/workflows/conversion-concurrency.ts#conversionsAtOnce
  - kind: code
    role: implementation
    target: src/main/keep-awake.ts#KeepAwake
  - kind: adr
    role: intent
    target: docs/adr/0065-a-queue-is-a-signal-the-window-gives-the-main-process.md
  - kind: adr
    role: intent
    target: docs/adr/0068-how-many-are-converted-at-once-is-a-choice-a-queue-keeps.md
---

# Change Processing settings

Sets what Mangabound does while it converts, under While Mangabound converts: Tell me when a long conversion ends, Keep the computer awake while converting, and Parallel conversions. A change applies from the next press of Process.
