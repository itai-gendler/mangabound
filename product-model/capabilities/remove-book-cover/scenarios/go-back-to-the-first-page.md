---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User removes the cover of volume 1
    kind: actor
    actor: user
    entities:
      - entity: book-cover
        effect: reads
        facts:
          - Book
          - Image name
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::book-details
  - text: The Product drops the Book cover and its copy
    kind: product
    actor: user
    entities:
      - entity: book-cover
        effect: removes
    contexts:
      desktop:
        place: desktop::book-details
---

# Go back to the first page

## Trigger

The User prefers the book's own first page.

## Outcome

The line shows First page for that book.
