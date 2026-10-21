---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User picks 90 days and chooses Delete…
    kind: actor
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The tab says nothing has waited for more than 90 days, and nothing is asked
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
---

# Nothing waited that long

## Trigger

Every pending conversion is recent.

## Outcome

Nothing is deleted.
