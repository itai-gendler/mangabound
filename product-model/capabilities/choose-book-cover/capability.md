---
availability:
  - place: desktop
domain: book-details
references:
  - kind: code
    role: implementation
    target: src/domain/book-covers.ts#looksLikeCoverImage
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

# Choose a cover

Gives one book of an item an image of the User's own as its cover, with Choose cover… or Change… on its line, or by dropping an image on it.
