---
appliesTo:
  - type: capability
    id: edit-book-details
  - type: entity
    id: ready-book
    facts:
      - Author
references:
  - kind: doc
    role: intent
    target: website/src/content/docs/getting-started/overview.mdx
---

# Only an EPUB carries a language, and a CBZ carries no author

The language goes into EPUB books only, and the author into EPUB and PDF books; a CBZ carries neither, and its author is only shown in the catalog Mangabound serves.
