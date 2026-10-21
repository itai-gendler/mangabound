---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/domain/mapping-editor.ts#redoMappingCommand
  - kind: code
    role: implementation
    target: src/domain/mapping-editor.ts#applyMappingCommand
  - kind: code
    role: implementation
    target: src/renderer/components/mapping/mapping-editor.tsx#MappingEditor
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/mapping-editor.mdx
---

# Redo a mapping edit

Applies again an edit that was undone, until a new edit is made.
