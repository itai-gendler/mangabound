---
kind: primary
routes:
  opds: OPDS catalog
steps:
  - text: The OPDS reader opens the catalog address
    kind: actor
    actor: opds-reader
    entities: []
    contexts:
      opds:
        place: opds
  - text: The Product answers with the root of the OPDS catalog, which leads to Recently converted and Other files
    kind: product
    actor: opds-reader
    entities:
      - entity: opds-catalog
        effect: reads
        facts:
          - What is shared
    contexts:
      opds:
        place: opds
  - text: The OPDS reader opens Recently converted
    kind: actor
    actor: opds-reader
    entities: []
    contexts:
      opds:
        place: opds
  - text: The Product lists every Ready book of every Pending conversion, newest first, with its title and author
    kind: product
    actor: opds-reader
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Title
          - Author
          - Format
          - Made at
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
    contexts:
      opds:
        place: opds
---

# List the recently converted books

## Trigger

The ready books are shared and KOReader has the catalog address.

## Outcome

The reader sees the latest books first, including any converted after sharing started.
