---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User changes the author of a folder on a read-only drive and leaves the page
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        facts:
          - Author
    contexts:
      desktop:
        place: desktop::book-details
  - text: The details cannot be written into the folder; a notice says so, and the Queue item keeps them for this session
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Author
    contexts:
      desktop:
        place: desktop::queue
---

# The folder cannot keep the details

## Trigger

The folder cannot be written, or its mangabind.json is not valid.

## Outcome

The books of this session still carry the author; only keeping it for next time failed, and nothing else is stopped.
