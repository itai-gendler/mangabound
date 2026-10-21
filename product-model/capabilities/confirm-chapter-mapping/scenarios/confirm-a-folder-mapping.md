---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User confirms a Chapter mapping whose ready check says all chapters are ready to bind
    kind: actor
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Unassigned chapters
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Chapter mapping becomes the grouping of the Queue item, and the User is back on the queue
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

# Confirm a manga folder's mapping

## Trigger

The volumes in the editor are the ones the User wants.

## Outcome

The row shows its volumes and is ready to process with them.
