---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User stops sharing
    kind: actor
    actor: user
    entities:
      - entity: opds-catalog
        effect: reads
        facts:
          - Catalog address
    contexts:
      desktop:
        place: desktop::share-panel
  - text: The OPDS catalog stops answering, and any download still running ends
    kind: product
    actor: user
    entities:
      - entity: opds-catalog
        effect: changes
        from: Sharing
        to: Stopped
        facts: []
    contexts:
      desktop:
        place: desktop::share-panel
---

# Stop the catalog

## Trigger

The e-reader has what it needs.

## Outcome

Nothing is served; the pending conversions can be deleted again, and the working folder changed.
