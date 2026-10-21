---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User adds covers from a folder of three images for three volumes
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
  - text: The Product gives the images, in order of name, to the books in volume order, each as a Book cover from a folder
    kind: product
    actor: user
    entities:
      - entity: book-cover
        effect: creates
        facts:
          - Book
          - Image name
          - Origin
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::book-details
---

# Covers in name order

## Trigger

The User has a folder of covers for the whole series.

## Outcome

Each book has its cover, marked as from a folder; 2.jpg comes before 10.jpg.
