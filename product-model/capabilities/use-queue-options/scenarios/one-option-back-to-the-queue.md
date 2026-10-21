---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User chooses Use the queue's value beside the item's device
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Own options
    contexts:
      desktop:
        place: desktop::item-options
  - text: The item's device follows the queue again, and with it the upscaling and color that device starts with
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

# One option back to the queue's value

## Trigger

Only one of the options an item set should go.

## Outcome

The item keeps its other options of its own.
