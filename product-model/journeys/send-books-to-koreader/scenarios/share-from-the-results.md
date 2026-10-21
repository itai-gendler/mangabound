---
kind: primary
result: achieved
routes:
  desktop: Desktop
steps:
  - text: The User chooses Share these books in the results
    kind: actor
    actor: user
    capability: share-ready-books
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
  - text: The OPDS catalog is set to the ready books and the Share panel opens
    kind: product
    actor: user
    capability: share-ready-books
    entities:
      - entity: opds-catalog
        effect: changes
        facts:
          - What is shared
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::share-panel
  - text: The User picks the network interface and starts sharing
    kind: actor
    actor: user
    capability: start-sharing
    entities:
      - entity: opds-catalog
        effect: changes
        facts:
          - Network interface
    contexts:
      desktop:
        place: desktop::share-panel
  - text: The OPDS catalog answers at its address, shown to copy
    kind: product
    actor: user
    capability: start-sharing
    entities:
      - entity: opds-catalog
        effect: changes
        from: Stopped
        to: Sharing
        facts:
          - Catalog address
    contexts:
      desktop:
        place: desktop::share-panel
---

# Share from the results

## Trigger

A run just made books and the e-reader is on the same network.

## Outcome

KOReader can open the catalog address and download the books while Mangabound stays open.
