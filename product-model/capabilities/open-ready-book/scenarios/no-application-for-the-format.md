---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User opens a CBZ Ready book on a computer with no comic reader
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
  - text: The results say the book could not be opened
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::results
---

# No application for the format

## Trigger

The system has no application set for the format.

## Outcome

Nothing opens; installing a compatible reader, or choosing one in the system settings, fixes it.
