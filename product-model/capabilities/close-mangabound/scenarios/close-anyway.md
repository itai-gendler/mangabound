---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User closes Mangabound while a conversion runs and chooses Close anyway
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::processing
  - text: The running conversion stops; the Ready book being made is lost, and those already finished stay in the Pending conversion
    kind: product
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::processing
---

# Close anyway during a conversion

## Trigger

The User has to leave before the run ends.

## Outcome

The app closes; the books finished before it stay under Ready books for the next launch.
