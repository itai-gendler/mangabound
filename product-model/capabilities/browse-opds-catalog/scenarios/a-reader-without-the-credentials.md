---
kind: validation
routes:
  opds: OPDS catalog
steps:
  - text: The OPDS reader opens the catalog without the username and password it was shared with
    kind: actor
    actor: opds-reader
    entities:
      - entity: opds-reader
        effect: reads
        facts:
          - Username sent
          - Password sent
    contexts:
      opds:
        place: opds
  - text: The Product asks for them and lists nothing
    kind: condition
    actor: opds-reader
    entities:
      - entity: opds-catalog
        effect: reads
        facts:
          - Username
          - Password
    contexts:
      opds:
        place: opds
---

# A reader without the username and password

## Trigger

Sharing was started with a username and password.

## Outcome

The reader is asked to sign in; filling in the same credentials in its catalog entry lets it in.
