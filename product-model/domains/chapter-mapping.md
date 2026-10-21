---
references:
  - kind: adr
    role: intent
    target: docs/adr/0008-mapping-starts-from-mangabind-grouping.md
---

# Volume mapping

The volume editor: which chapters of a manga belong in each volume, read from the file names, built by hand, or suggested by an online source, and confirmed for the run.

## Boundary

It owns the volumes of a manga and their chapters. It does not own how the volumes are converted, nor the title, author or language of the books.
