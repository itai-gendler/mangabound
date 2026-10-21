---
appliesTo:
  - type: capability
    id: edit-book-details
  - type: capability-scenario
    id: make-the-books-of-a-folder
  - type: entity
    id: queue-item
    facts:
      - Title
references:
  - kind: code
    role: implementation
    target: src/domain/book-details.ts#volumeBookTitle
  - kind: code
    role: implementation
    target: src/domain/book-details.ts#maxTitleBytes
  - kind: adr
    role: intent
    target: docs/adr/0030-title-author-and-language-belong-to-each-book.md
---

# A series title names each volume with its number

A Series title typed for a folder titles each of its books Title - Vol.01, Title - Vol.02 and so on; a Book title names the one book of a CBZ, a folder converted whole or a series made into one book. Left empty, the folder's or file's name is used. A title holds at most 200 bytes, since its book's file is named after it, and a language tag is written in its standard form, so pt-br becomes pt-BR.
