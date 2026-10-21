---
availability:
  - place: desktop
domain: book-details
references:
  - kind: code
    role: implementation
    target: src/application/workflows/book-covers.ts#BookCovers
  - kind: code
    role: implementation
    target: src/main/ipc/covers.ts#registerCoverHandlers
  - kind: adr
    role: intent
    target: docs/adr/0040-a-cover-of-the-persons-own-for-each-book.md
---

# Remove a cover

Takes the cover of one book away, so that it uses its first page again.
