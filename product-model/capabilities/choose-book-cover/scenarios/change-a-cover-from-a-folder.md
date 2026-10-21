---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User drops an image on a book whose Book cover came from a folder
    kind: actor
    actor: user
    entities:
      - entity: book-cover
        effect: reads
        facts:
          - Book
          - Origin
    contexts:
      desktop:
        place: desktop::book-details
  - text: The image becomes that book's cover, now chosen by hand
    kind: product
    actor: user
    entities:
      - entity: book-cover
        effect: changes
        facts:
          - Image name
          - Origin
    contexts:
      desktop:
        place: desktop::book-details
---

# Change a cover that came from a folder

## Trigger

One image from the folder is the wrong one.

## Outcome

That book has the new image, and a later folder will not replace it.
