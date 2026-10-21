---
appliesTo:
  - type: capability
    id: add-covers-from-folder
  - type: capability
    id: choose-book-cover
  - type: entity
    id: book-cover
    facts:
      - Origin
references:
  - kind: code
    role: implementation
    target: src/domain/book-covers.ts#planFolderImport
  - kind: adr
    role: intent
    target: docs/adr/0040-a-cover-of-the-persons-own-for-each-book.md
---

# A cover chosen by hand is never replaced by a folder

Covers from a folder go to the books in name order; the image that falls on a book with a cover chosen by hand is passed over, while a cover an earlier folder gave is replaced. An image that cannot be read keeps its place in the order, so the images after it still reach the books they line up with.
