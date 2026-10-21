---
appliesTo:
  - type: capability
    id: start-sharing
  - type: entity
    id: opds-catalog
    facts:
      - Network interface
      - Catalog address
references:
  - kind: code
    role: implementation
    target: src/main/ipc/opds.ts#registerOpdsHandlers
  - kind: adr
    role: intent
    target: docs/adr/0019-opds-server-binds-a-fixed-port.md
---

# The catalog is served only on the chosen network interface, at port 48123

Sharing starts only on one of the network interfaces the panel lists, always at port 48123, so a catalog added once in KOReader keeps working while the address stays the same. There is one share at a time, it answers only to the computer's own addresses and names, and it drops a connection that has been silent for a minute.
