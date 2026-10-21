---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses an image for the book of volume 2
    kind: actor
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::book-details
  - text: The Product checks that the file really is a JPEG, PNG, WebP, GIF or BMP image, keeps a copy and makes it that book's Book cover
    kind: product
    actor: user
    entities:
      - entity: book-cover
        effect: creates
        facts:
          - Book
          - Image name
          - Origin
    contexts:
      desktop:
        place: desktop::book-details
---

# Choose a cover for a volume

## Trigger

The first page of the volume is not the cover the User wants.

## Outcome

Volume 2's book will use the image as its cover; the original can now be moved or deleted.
