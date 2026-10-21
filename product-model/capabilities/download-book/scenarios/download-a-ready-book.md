---
kind: primary
routes:
  opds: OPDS catalog
steps:
  - text: The OPDS reader downloads a Ready book from Recently converted
    kind: actor
    actor: opds-reader
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
          - Format
    contexts:
      opds:
        place: opds
  - text: The Product sends the file in its format
    kind: product
    actor: opds-reader
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
          - Format
          - Size
    contexts:
      opds:
        place: opds
---

# Download a ready book

## Trigger

The person picked a book in KOReader and tapped its format.

## Outcome

The book is stored on the e-reader and can be read with Mangabound closed.
