---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Save all to folder… and picks a folder
    kind: actor
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
  - text: The Product copies each Ready book under a free name, records it in the catalog of that Library folder, and marks it saved
    kind: product
    actor: user
    entities:
      - entity: ready-book
        effect: changes
        from: Not saved yet
        to: Saved
        facts:
          - Saved to
      - entity: library-folder
        effect: changes
        facts:
          - Recorded books
    contexts:
      desktop:
        place: desktop::results
---

# Save every book of a run

## Trigger

The run made several books and the User wants them all in one place.

## Outcome

Every book is in the folder; a name already taken got a numbered copy, such as Name (2).epub, so saving twice leaves extra copies.
