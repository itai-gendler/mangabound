---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User removes a manga folder from the queue
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product drops the Queue item with its Chapter mapping and every Volume, and frees the copy it read the folder from
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: removes
        from: Read
      - entity: chapter-mapping
        effect: removes
        from: Proposed
        with: queue-item
      - entity: volume
        effect: removes
        with: chapter-mapping
    contexts:
      desktop:
        place: desktop::queue
---

# Remove a manga folder

## Trigger

The User no longer wants a folder in this run.

## Outcome

The folder is gone from the queue, with what was typed and chosen for it in this session. Nothing in the folder was deleted, and its covers come back if it is added again.
