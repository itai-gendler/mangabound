---
kind: alternate
routes:
  opds: OPDS catalog
steps:
  - text: The OPDS reader downloads a book listed in a shared Library folder
    kind: actor
    actor: opds-reader
    entities:
      - entity: library-folder
        effect: reads
        facts:
          - Recorded books
    contexts:
      opds:
        place: opds
  - text: The Product sends the file, which it finds inside the shared folder
    kind: product
    actor: opds-reader
    entities:
      - entity: library-folder
        effect: reads
        facts:
          - Recorded books
          - Other files
    contexts:
      opds:
        place: opds
---

# Download from a shared library folder

## Trigger

A folder of saved books is shared.

## Outcome

The book is on the e-reader; a book the catalog names outside the shared folder is answered as not found.
