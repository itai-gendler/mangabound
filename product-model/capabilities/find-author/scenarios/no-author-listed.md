---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User looks at a match that lists no author
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Title
    contexts:
      desktop:
        place: desktop::book-details
  - text: The match says No author listed and offers nothing to use
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::book-details
---

# The work lists no author

## Trigger

The source knows the work but not who wrote it.

## Outcome

The author field stays as it was; the User can type it.
