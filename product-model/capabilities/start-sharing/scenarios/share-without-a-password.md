---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User selects the network interface the e-reader can reach and leaves Username and Password empty
    kind: actor
    actor: user
    entities:
      - entity: opds-catalog
        effect: changes
        facts:
          - Network interface
    contexts:
      desktop:
        place: desktop::share-panel
  - text: The User starts sharing
    kind: actor
    actor: user
    entities:
      - entity: opds-catalog
        effect: reads
        facts:
          - What is shared
    contexts:
      desktop:
        place: desktop::share-panel
  - text: The OPDS catalog answers on that interface at port 48123, and the panel shows its address to copy
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

# Share without a password

## Trigger

The User wants to download books on the e-reader over the home network.

## Outcome

The catalog address, such as http://192.168.1.150:48123/, is shown with Copy; the interface chosen is remembered for next time, and the same address keeps working while the computer's address stays the same.
