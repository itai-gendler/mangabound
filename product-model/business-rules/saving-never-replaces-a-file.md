---
appliesTo:
  - type: capability
    id: save-all-books
  - type: capability
    id: save-book-as
references:
  - kind: code
    role: implementation
    target: src/library/pending-save.ts#saveWithUniqueName
  - kind: code
    role: implementation
    target: src/main/ipc/pending-decisions.ts#wrongExtension
---

# Save all to folder never replaces an existing file

Save all to folder gives a book whose name is taken the next free numbered name, so a repeated save adds copies. Save as… uses the system's save dialog, which asks before replacing a file, and the name must keep the book's own extension.
