---
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
    target: src/adapters/covers/fs-cover-store.ts#FsCoverStore
  - kind: adr
    role: intent
    target: docs/adr/0040-a-cover-of-the-persons-own-for-each-book.md
---

# Book cover

An image of the person's own that one book of an item uses as its cover instead of its first page. Mangabound keeps its own copy, filed under the item's folder or file, so the original can be moved or deleted and the cover comes back the next time the item is added.

## Information kept

- **Book** — which book it is for: a volume by its number, or the one book an item makes
- **Image name** — the name the image had where it was picked
- **Origin** — chosen for that book by hand, or taken from a folder in name order
