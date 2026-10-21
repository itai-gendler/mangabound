---
appliesTo:
  - type: capability
    id: process-queue
  - type: entity
    id: ready-book
    facts:
      - Name
references:
  - kind: code
    role: implementation
    target: src/library/unique-name.ts#uniqueFileName
  - kind: adr
    role: intent
    target: docs/adr/0029-books-of-one-run-never-replace-each-other.md
---

# A book of a run never replaces another

Two books of one run that would have the same name each get one: the second is named with a number, Name (2).epub, and a Kobo's .kepub.epub keeps its ending. A book that would have replaced the file it was made from gets another name, and its results say so.
