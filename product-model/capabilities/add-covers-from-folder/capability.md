---
availability:
  - place: desktop
domain: book-details
references:
  - kind: code
    role: implementation
    target: src/domain/book-covers.ts#planFolderImport
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

# Add covers from a folder

Gives the books of an item the images of a folder in order of name, the first image to the first book, with Add covers from a folder… or by dropping a folder or several images on the list.
