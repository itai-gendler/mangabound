---
references:
  - kind: adr
    role: intent
    target: docs/adr/0018-opds-basic-auth-only-optionally-blank.md
---

# Sharing

The Share panel: what is served to the e-reader, on which network interface and with which credentials, and turning the catalog on and off.

## Boundary

It owns the OPDS catalog's setup and whether it runs. It does not own the books it serves, nor what the reader does with the catalog, which happens on the reader's side of the OPDS feed.
