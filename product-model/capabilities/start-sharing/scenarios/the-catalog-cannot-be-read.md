---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User starts sharing a Library folder whose catalog is damaged
    kind: actor
    actor: user
    entities:
      - entity: library-folder
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::share-panel
  - text: Sharing does not start, and the panel says the library catalog could not be read
    kind: condition
    actor: user
    entities:
      - entity: opds-catalog
        effect: reads
        facts:
          - What is shared
    contexts:
      desktop:
        place: desktop::share-panel
---

# The folder's catalog cannot be read

## Trigger

The catalog file in the shared folder is not one Mangabound can read.

## Outcome

Nothing is served rather than a broken catalog on the reader.
