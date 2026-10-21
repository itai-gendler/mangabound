---
appliesTo:
  - type: capability
    id: edit-book-details
  - type: capability-scenario
    id: add-a-manga-folder
  - type: entity
    id: queue-item
    facts:
      - Author
      - Language
references:
  - kind: code
    role: implementation
    target: src/domain/book-details.ts#persistableDetails
  - kind: adr
    role: intent
    target: docs/adr/0032-keep-the-author-and-language-with-the-folder.md
---

# The author and language are kept with the folder; the title is not

When the details page of a folder or library title is left after the author or language changed, both are written under manga in the folder's mangabind.json, and they come back whenever the folder is read. The title is typed for the run only. A CBZ has no folder to keep them in. If the folder cannot be written, a notice says so and the details still apply for the session.
