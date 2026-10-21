---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User drops a folder on the queue
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product adds a Queue item for the folder and starts reading it
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: creates
        to: Checking
        facts:
          - Kind
          - Name
          - Location
    contexts:
      desktop:
        place: desktop::queue
  - text: mangabind cannot read the folder, and the Product keeps what it said
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        from: Checking
        to: Could not read
        facts:
          - Read problem
    contexts:
      desktop:
        place: desktop::queue
  - text: The row says it could not be read, and why
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
          - Read problem
    contexts:
      desktop:
        place: desktop::queue
---

# An item that cannot be read

## Trigger

A folder or CBZ added to the queue cannot be read.

## Outcome

The item stays in the queue as Could not read, with the reason in the tool's or the system's words, and a run leaves it out.
