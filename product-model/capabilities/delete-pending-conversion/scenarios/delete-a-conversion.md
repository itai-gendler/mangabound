---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Delete on a Pending conversion under Ready books
    kind: actor
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Made at
          - Books
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
  - text: The User confirms that its pending books are to be deleted
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product deletes the Pending conversion with every Ready book in it
    kind: product
    actor: user
    entities:
      - entity: pending-conversion
        effect: removes
      - entity: ready-book
        effect: removes
        from: Not saved yet
        with: pending-conversion
    contexts:
      desktop:
        place: desktop::queue
---

# Delete a conversion

## Trigger

The books of an earlier run are no longer wanted, or were saved already.

## Outcome

The conversion is gone from Ready books and its room is free; getting its books again means processing the source again.
