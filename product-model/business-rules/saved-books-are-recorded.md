---
appliesTo:
  - type: capability
    id: save-book-as
  - type: capability
    id: save-all-books
  - type: capability
    id: browse-opds-catalog
references:
  - kind: code
    role: implementation
    target: src/adapters/library/fs-pending-runs.ts#FsPendingRuns
  - kind: adr
    role: intent
    target: docs/adr/0007-library-indexing-and-opds-delivery.md
---

# A saved book is recorded in its folder's catalog

Every book saved into a folder is recorded in a catalog kept inside that folder, with its title, author, format, size and when it was converted, and sharing that folder lists it under Recently converted. A book is saved only once the copy, the record in the catalog and the pending copy's note of it all succeed; when only the copy succeeded, the person is told to check the folder before saving again.
