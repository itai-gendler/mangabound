---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Save as… beside a Ready book
    kind: actor
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
          - Format
    contexts:
      desktop:
        place: desktop::results
  - text: The User picks a name and a folder in the save dialog
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::results
  - text: The Product copies the Ready book there, records it in the catalog of that Library folder, and marks it saved
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

# Save one book

## Trigger

The User wants a book on their own disk or ready to copy to the e-reader.

## Outcome

The copy is where the User put it, the book shows Saved with Show in folder, and the folder's catalog lists it for sharing. The dialog starts in the last folder used.
