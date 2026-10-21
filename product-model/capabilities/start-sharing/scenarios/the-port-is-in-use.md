---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User starts sharing while another program holds port 48123
    kind: actor
    actor: user
    entities:
      - entity: opds-catalog
        effect: reads
        facts:
          - Network interface
    contexts:
      desktop:
        place: desktop::share-panel
  - text: The OPDS catalog does not start, and the panel says the port is in use
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

# The port is in use

## Trigger

Something else on the computer already answers on that port.

## Outcome

Sharing stays stopped; the port is fixed so that a catalog added once in KOReader keeps working.
