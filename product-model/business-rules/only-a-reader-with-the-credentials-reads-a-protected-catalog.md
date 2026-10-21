---
appliesTo:
  - type: entity
    id: ready-book
    effect: reads
    contexts:
      - place: opds
  - type: entity
    id: library-folder
    effect: reads
    contexts:
      - place: opds
permits:
  - actors:
      - opds-reader
    when:
      - entity: opds-catalog
        fact: Username
        absent: true
      - entity: opds-catalog
        fact: Password
        absent: true
  - actors:
      - opds-reader
    when:
      - entity: opds-reader
        fact: Username sent
        is:
          entity: opds-catalog
          fact: Username
      - entity: opds-reader
        fact: Password sent
        is:
          entity: opds-catalog
          fact: Password
references:
  - kind: code
    role: implementation
    target: src/adapters/opds/http-server.ts#NodeOpdsServer
  - kind: adr
    role: intent
    target: docs/adr/0018-opds-basic-auth-only-optionally-blank.md
---

# Only a reader with the username and password reads a catalog shared with them

A catalog shared with both fields empty answers any reader that reaches it; one shared with a username and password answers only a reader that sends both.
