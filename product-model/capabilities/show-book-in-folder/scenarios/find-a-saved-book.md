---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User shows a saved Ready book in its folder
    kind: actor
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
          - Saved to
    contexts:
      desktop:
        place: desktop::results
  - text: The file manager opens on the folder of the saved copy, with it selected
    kind: product
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Saved to
    contexts:
      desktop:
        place: desktop::results
---

# Find a saved book

## Trigger

The User wants to copy the saved book somewhere else.

## Outcome

The saved copy is in front of the User.
