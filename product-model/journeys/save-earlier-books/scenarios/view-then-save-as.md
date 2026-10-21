---
kind: primary
result: achieved
routes:
  desktop: Desktop
steps:
  - text: The User opens View books on a Pending conversion under Ready books
    kind: actor
    actor: user
    capability: view-conversion-books
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
  - text: The results list its Ready book, not saved yet
    kind: condition
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
  - text: The User chooses Save as… and picks a name and folder
    kind: actor
    actor: user
    capability: save-book-as
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
  - text: The Ready book is copied, recorded in the Library folder and marked saved
    kind: product
    actor: user
    capability: save-book-as
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

# View the conversion, then save a book

## Trigger

Mangabound was closed before a run's books were saved.

## Outcome

The book is saved; once every book of that conversion is saved, closing the app removes the conversion.
