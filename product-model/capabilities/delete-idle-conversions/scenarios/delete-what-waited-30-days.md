---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User picks 30 days and chooses Delete…
    kind: actor
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
          - Size
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The question says how many conversions, books and how much room would go, and that unsaved books will be lost
    kind: condition
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
          - Size
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The User confirms
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The Product deletes each Pending conversion untouched for that long, with every Ready book in it
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
        place: desktop::app-settings
---

# Delete what waited more than 30 days

## Trigger

Old conversions are taking room.

## Outcome

The tab says how many conversions and how much room were deleted; newer conversions stay.
