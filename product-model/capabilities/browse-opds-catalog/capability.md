---
availability:
  - place: opds
references:
  - kind: code
    role: implementation
    target: src/opds/feed.ts#buildAcquisitionFeed
  - kind: code
    role: implementation
    target: src/adapters/library/pending-catalog-store.ts
  - kind: code
    role: implementation
    target: src/adapters/opds/http-server.ts#NodeOpdsServer
  - kind: adr
    role: intent
    target: docs/adr/0007-library-indexing-and-opds-delivery.md
  - kind: adr
    role: intent
    target: docs/adr/0020-opds-also-lists-untracked-files.md
  - kind: doc
    role: intent
    target: website/src/content/docs/koreader/connecting.mdx
---

# Browse the catalog

Lets an OPDS reader on the network list what is shared: Recently converted, newest first, with the title and author Mangabound recorded, and Other files, the books in the folder it did not record.
