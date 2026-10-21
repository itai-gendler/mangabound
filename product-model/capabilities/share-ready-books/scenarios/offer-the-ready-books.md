---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Share these books in the results
    kind: actor
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
  - text: The OPDS catalog is set to share every Ready book of every Pending conversion, and the Share panel opens
    kind: product
    actor: user
    entities:
      - entity: opds-catalog
        effect: changes
        facts:
          - What is shared
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::share-panel
---

# Offer the ready books to the e-reader

## Trigger

The User wants the books on the e-reader without saving them first.

## Outcome

The Share panel shows the books ready to share, waiting for Start sharing.
