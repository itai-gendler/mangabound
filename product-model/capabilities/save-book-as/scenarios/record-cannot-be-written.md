---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User saves a Ready book into a folder whose catalog cannot be written
    kind: actor
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
  - text: The Product copies the book but cannot record it in the Library folder, and says so
    kind: product
    actor: user
    entities:
      - entity: library-folder
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
---

# The copy is made but cannot be recorded

## Trigger

The catalog file in the destination is damaged or cannot be written.

## Outcome

A notice says the book may have been copied although its record failed, so the folder should be checked before saving again; the pending copy stays available.
