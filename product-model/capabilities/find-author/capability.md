---
availability:
  - place: desktop
domain: book-details
references:
  - kind: code
    role: implementation
    target: src/renderer/components/details/author-lookup.tsx#AuthorLookupPanel
  - kind: code
    role: implementation
    target: src/adapters/metadata-providers/mangadex/provider.ts#MangaDexProvider
  - kind: adr
    role: intent
    target: docs/adr/0031-look-up-the-author-in-a-source-the-person-chooses.md
---

# Find author

Looks the author up by title in an online source the User picks, one search at a time, and fills the Author field with the one chosen.
