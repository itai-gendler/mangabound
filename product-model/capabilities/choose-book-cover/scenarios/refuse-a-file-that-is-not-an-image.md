---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User chooses a damaged file named cover.jpg
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::book-details
  - text: The page says the file cannot be read as an image, and the book keeps its first page
    kind: condition
    actor: user
    entities:
      - entity: book-cover
        effect: reads
        facts:
          - Book
    contexts:
      desktop:
        place: desktop::book-details
---

# A file that is not an image

## Trigger

The file has an image's name but does not hold one.

## Outcome

No cover is attached; the page lists the kinds of image a cover can be.
