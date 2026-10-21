---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Use the queue's options for one item
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
          - Own options
    contexts:
      desktop:
        place: desktop::item-options
  - text: The Queue item has no options of its own any more
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        facts:
          - Own options
    contexts:
      desktop:
        place: desktop::item-options
---

# One item follows the queue again

## Trigger

The item no longer needs to differ.

## Outcome

The page says the item uses the options of the queue, and its row button is plain again.
