---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User confirms deleting a Pending conversion while a queue is being processed
    kind: actor
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
    contexts:
      desktop:
        place: desktop::queue
  - text: Nothing is deleted, and the message says to wait for the current conversion to finish
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
---

# Not while a conversion runs

## Trigger

A run is making books in the meantime.

## Outcome

The conversion and its books stay; a conversion whose books are being saved is not deleted either.
