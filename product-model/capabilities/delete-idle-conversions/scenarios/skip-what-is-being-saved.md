---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User confirms the clean-up while the books of an old Pending conversion are being saved
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
  - text: That conversion is left out of the clean-up, and the tab says nothing was deleted because what was found is being saved
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
---

# A conversion being saved is skipped

## Trigger

The only old conversion is being saved from at that moment.

## Outcome

The conversion stays; the clean-up can be run again once the save ends. While the ready books are shared or a conversion runs, nothing is deleted at all.
