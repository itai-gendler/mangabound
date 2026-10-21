---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User adds a folder of covers to books of which one has a cover chosen by hand
    kind: actor
    actor: user
    entities:
      - entity: book-cover
        as: chosen
        effect: reads
        facts:
          - Book
          - Origin
    contexts:
      desktop:
        place: desktop::book-details
  - text: The image that falls on the hand-chosen Book cover is passed over, and the others go to the books they line up with, replacing covers an earlier folder gave
    kind: product
    actor: user
    entities:
      - entity: book-cover
        as: new
        effect: creates
        facts:
          - Book
          - Image name
          - Origin
      - entity: book-cover
        as: from-folder
        effect: changes
        facts:
          - Image name
    contexts:
      desktop:
        place: desktop::book-details
  - text: A note says how many covers chosen by hand were kept
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::book-details
---

# A cover chosen by hand stays

## Trigger

Some books already have covers.

## Outcome

Hand-chosen covers are untouched; covers from the earlier folder are replaced; an unreadable image keeps its place in the order and its book keeps its first page.

## Edge cases

- More images than books leaves the extra ones unused, and fewer leaves the last books with their first page; a note says which.
