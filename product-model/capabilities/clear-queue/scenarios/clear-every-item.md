---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User clears the queue
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product drops every Queue item, with its Chapter mapping and every Volume
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: removes
        from: Read
      - entity: chapter-mapping
        effect: removes
        from: Confirmed
        with: queue-item
      - entity: volume
        effect: removes
        with: chapter-mapping
    contexts:
      desktop:
        place: desktop::queue
---

# Clear every item

## Trigger

The User wants to start the queue over.

## Outcome

The queue is empty; Ready books still lists the pending conversions of earlier runs.
