---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User fills in both Username and Password and starts sharing
    kind: actor
    actor: user
    entities:
      - entity: opds-catalog
        effect: changes
        facts:
          - Network interface
          - Username
          - Password
    contexts:
      desktop:
        place: desktop::share-panel
  - text: The OPDS catalog answers only a reader that sends them
    kind: product
    actor: user
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

# Share with a username and password

## Trigger

Others use the same network.

## Outcome

KOReader needs the same username and password in its catalog entry.
