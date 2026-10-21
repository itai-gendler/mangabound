---
domain: sharing
singleton: true
references:
  - kind: code
    role: implementation
    target: src/main/ipc/opds.ts#registerOpdsHandlers
  - kind: code
    role: implementation
    target: src/main/ipc/sharing-target.ts#sharingTarget
  - kind: code
    role: implementation
    target: src/main/constants.ts#opdsPort
  - kind: adr
    role: intent
    target: docs/adr/0022-remember-chosen-network-interface.md
---

# OPDS catalog

Mangabound's one catalog on the local network: what it serves, where, and with which credentials. There is one at a time, and it ends when the app closes.

## Information kept

- **What is shared** — the ready books of every pending conversion, or a library folder the person chose
- **Network interface** — the interface it is served on; the one chosen is kept across launches
- **Username** — optional; with Username and Password both empty, the catalog asks for nothing
- **Password** — optional, asked for with the username
- **Catalog address** — the address to add in KOReader, such as http://192.168.1.150:48123/

## States

### Stopped

Nothing is served.

### Sharing

The catalog answers on the chosen interface while Mangabound is open.
