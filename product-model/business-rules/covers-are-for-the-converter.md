---
appliesTo:
  - type: capability
    id: choose-book-cover
  - type: capability-scenario
    id: make-the-books-of-a-folder
  - type: capability-scenario
    id: only-join-volumes
references:
  - kind: code
    role: implementation
    target: src/application/workflows/book-production.ts#withCovers
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/adding-manga.mdx
---

# Covers apply only where mangapress makes the books

A cover of the person's own is used only when mangapress makes the book: a run that only groups chapters uses none, and a PDF has no cover. A CBZ keeps a cover of its own whatever the cover options are. A cover that can no longer be used when its book is made fails that book, naming it.
