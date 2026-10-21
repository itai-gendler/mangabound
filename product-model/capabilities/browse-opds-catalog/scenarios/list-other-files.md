---
kind: alternate
routes:
  opds: OPDS catalog
steps:
  - text: The OPDS reader opens Other files of a shared Library folder
    kind: actor
    actor: opds-reader
    entities:
      - entity: library-folder
        effect: reads
        facts:
          - Name
    contexts:
      opds:
        place: opds
  - text: The Product lists the EPUB, CBZ and PDF files directly in the folder that its catalog does not record, titled by file name with an unknown author
    kind: product
    actor: opds-reader
    entities:
      - entity: library-folder
        effect: reads
        facts:
          - Other files
    contexts:
      opds:
        place: opds
---

# List the other files of a shared folder

## Trigger

Books were copied into the shared folder by hand.

## Outcome

Those books can be downloaded too, with plainer details than the ones Mangabound recorded; files in subfolders are not listed.
