---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#unassignChapters
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

# Unassign chapters

Takes selected chapters out of their volumes, so that no book holds them.
