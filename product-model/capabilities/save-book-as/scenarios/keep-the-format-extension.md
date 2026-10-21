---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User types a name ending in .pdf for an EPUB Ready book
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
  - text: Nothing is saved, and the message asks for the extension of the book's own format
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::results
---

# A name with another extension

## Trigger

The name typed in the dialog does not end in the book's extension.

## Outcome

The book stays Not saved yet; saving again with the right extension works.
