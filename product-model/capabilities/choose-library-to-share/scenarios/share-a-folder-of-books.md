---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses a library to share in the Share panel and picks a folder
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::share-panel
  - text: The OPDS catalog is set to serve that Library folder under its name
    kind: product
    actor: user
    entities:
      - entity: opds-catalog
        effect: changes
        facts:
          - What is shared
      - entity: library-folder
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::share-panel
---

# Share a folder of books

## Trigger

The User keeps finished books in a folder of their own.

## Outcome

The panel names the folder, ready for Start sharing; Change shared library picks another.
