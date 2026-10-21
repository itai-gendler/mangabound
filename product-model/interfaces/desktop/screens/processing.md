---
entities:
  - entity: queue-item
    shows:
      - Name
  - entity: library-title
    shows:
      - Name
  - entity: volume
    shows:
      - Number
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/running-screen.tsx#RunningScreen
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/processing.mdx
---

# Processing progress

A run in progress: which item of how many, the stage (building volume files, converting, saving), the overall progress and, under Show details, each volume's progress; and Cancel conversion.
