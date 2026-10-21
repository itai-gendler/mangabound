---
type: api
actors:
  - opds-reader
references:
  - kind: code
    role: implementation
    target: src/adapters/opds/http-server.ts#NodeOpdsServer
  - kind: code
    role: implementation
    target: src/opds/feed.ts#buildNavigationFeed
  - kind: adr
    role: intent
    target: docs/adr/0007-library-indexing-and-opds-delivery.md
  - kind: adr
    role: intent
    target: docs/adr/0019-opds-server-binds-a-fixed-port.md
  - kind: doc
    role: intent
    target: website/src/content/docs/koreader/connecting.mdx
---

# OPDS catalog feed

The OPDS 1.2 catalog Mangabound serves on the chosen network interface while sharing is on: a root that leads to Recently converted and Other files, and a download for each book listed there. KOReader is the reader the guide sets up; any OPDS reader can use it.
