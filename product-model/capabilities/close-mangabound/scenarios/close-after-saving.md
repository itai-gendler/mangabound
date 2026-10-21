---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User closes Mangabound with nothing converting and sharing on
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The OPDS catalog stops, and every Pending conversion whose every Ready book was saved is removed with them
    kind: product
    actor: user
    entities:
      - entity: opds-catalog
        effect: changes
        from: Sharing
        to: Stopped
        facts: []
      - entity: pending-conversion
        effect: removes
      - entity: ready-book
        effect: removes
        from: Saved
        with: pending-conversion
    contexts:
      desktop:
        place: desktop::queue
---

# Close after the books were saved

## Trigger

The User is done for now.

## Outcome

The saved copies stay where they were saved; conversions with books not yet saved are kept for the next launch.
