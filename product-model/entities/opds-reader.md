---
kind: system
acts: external
references:
  - kind: doc
    role: intent
    target: website/src/content/docs/koreader/connecting.mdx
  - kind: code
    role: implementation
    target: src/adapters/opds/http-server.ts#NodeOpdsServer
---

# OPDS reader

KOReader, or another OPDS reader on an e-reader, that the person points at the catalog address to browse and download books over the local network.

## Information kept

- **Username sent** — the username the reader sends with each request, when it was given one
- **Password sent** — the password the reader sends with it
