---
availability:
  - place: desktop
domain: book-details
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/book-details-screen.tsx#BookDetailsScreen
  - kind: code
    role: implementation
    target: src/domain/book-details.ts#normalizeBookDetails
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/adding-manga.mdx
  - kind: code
    role: implementation
    target: src/domain/book-details.ts#persistableDetails
  - kind: code
    role: implementation
    target: src/adapters/mangabind/stored-details.ts#readStoredDetails
  - kind: adr
    role: intent
    target: docs/adr/0030-title-author-and-language-belong-to-each-book.md
  - kind: adr
    role: intent
    target: docs/adr/0032-keep-the-author-and-language-with-the-folder.md
---

# Edit title, author and language

Sets the Series title or Book title, the Author and the Language of one item or library title. Every field is optional; one left empty uses its default. Leaving the page keeps the author and language with a folder.
