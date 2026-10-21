---
entities:
  - entity: queue-item
    shows:
      - Name
      - Links not followed
  - entity: library-title
    shows:
      - Name
      - Folders left out
      - Failure reason
      - Own options
  - entity: chapter-mapping
    shows:
      - Chapters
      - Unassigned chapters
  - entity: volume
    shows:
      - Number
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/library-screen.tsx#LibraryScreen
  - kind: adr
    role: intent
    target: docs/adr/0012-libraries-in-the-queue.md
---

# Library titles

The manga of one library, opened with Edit titles on its row: each title with the volumes it would make, or that it needs volumes, was saved or failed, and the actions to group it, set its details or give it options of its own.
