---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User confirms deleting a Pending conversion while the ready books are being shared
    kind: actor
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
  - text: The OPDS catalog is sharing the ready books, so nothing is deleted and the message says to stop sharing first
    kind: condition
    actor: user
    entities:
      - entity: opds-catalog
        effect: reads
        facts:
          - What is shared
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
---

# Not while the ready books are shared

## Trigger

Sharing serves the ready books of every pending conversion.

## Outcome

The conversion and its books stay.
