---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User saves all the books into a folder on a drive that fills up part-way
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
  - text: The books that fit are copied, recorded and marked saved; each Ready book that failed is named with the reason
    kind: product
    actor: user
    entities:
      - entity: ready-book
        effect: changes
        from: Not saved yet
        to: Saved
        facts:
          - Saved to
      - entity: library-folder
        effect: changes
        facts:
          - Recorded books
    contexts:
      desktop:
        place: desktop::results
---

# Some books cannot be saved

## Trigger

The destination runs out of room, or a file cannot be written.

## Outcome

The saved books show Saved; the others stay Not saved yet and can be saved again once there is room.
