---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User opens a Ready book
    kind: actor
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
          - Format
    contexts:
      desktop:
        place: desktop::results
  - text: The system opens the file with the application it has for that format
    kind: product
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Saved to
    contexts:
      desktop:
        place: desktop::results
---

# Open in the default application

## Trigger

The User wants to check a book before saving or sharing it.

## Outcome

The book is open in the reader the system uses for EPUB, CBZ or PDF.
