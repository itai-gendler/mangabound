---
domain: sharing
references:
  - kind: code
    role: implementation
    target: src/adapters/library/fs-library-store.ts#FsLibraryStore
  - kind: code
    role: implementation
    target: src/library/publish.ts#publishBook
  - kind: adr
    role: intent
    target: docs/adr/0007-library-indexing-and-opds-delivery.md
  - kind: adr
    role: intent
    target: docs/adr/0020-opds-also-lists-untracked-files.md
---

# Library folder

A folder of finished books: one books were saved into, or one chosen in the Share panel to be served. Mangabound records every book saved into it in a catalog kept inside the folder, which sharing lists as Recently converted.

## Information kept

- **Name** — the folder's name, which the catalog is titled with
- **Recorded books** — each book saved there, with its title, author, format, size and when it was converted
- **Other files** — the EPUB, CBZ and PDF files directly in the folder that its catalog does not record
