---
appliesTo:
  - type: capability-scenario
    id: add-a-manga-folder
  - type: capability
    id: browse-library-titles
  - type: entity
    id: queue-item
    facts:
      - Folders left out
references:
  - kind: code
    role: implementation
    target: src/domain/unrecognized-chapters.ts
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/mapping-editor.mdx
---

# A folder whose name holds no chapter number is in no book

A chapter is known by the number in its folder name. A folder named without one, such as Omake, is listed under Folders left out on the row and in the editor, and the editor cannot place it; renaming it and adding the item again brings it in.
