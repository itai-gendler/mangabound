---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User opens the book details of a manga folder
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
  - text: The User types the series title, the author and the language
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        facts:
          - Title
          - Author
          - Language
    contexts:
      desktop:
        place: desktop::book-details
  - text: Books will be titled with the series title and the number of each Volume
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Title
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::book-details
  - text: Leaving the page keeps the author and language of the Queue item in the folder's mangabind.json; the title is not kept
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Author
          - Language
    contexts:
      desktop:
        place: desktop::queue
---

# Name a series and its author

## Trigger

The folder's name is not the title the User wants on the books.

## Outcome

Each volume's book will be titled Title - Vol.01 and so on, carry the author, and, as an EPUB, the language. The next time the folder is added, its author and language are already there.
