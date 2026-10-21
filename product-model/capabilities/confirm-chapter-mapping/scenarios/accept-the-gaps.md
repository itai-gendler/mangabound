---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User confirms a Chapter mapping whose ready check warns of two unassigned chapters
    kind: actor
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Chapter mapping is confirmed with the gaps, and the row of the Queue item says two chapters are left out
    kind: product
    actor: user
    entities:
      - entity: chapter-mapping
        effect: changes
        from: Proposed
        to: Confirmed
        facts: []
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
---

# Confirm with chapters left unassigned

## Trigger

Some chapters are not meant to be in any book.

## Outcome

The item runs with the volumes it has, and its unassigned chapters are in no book.
