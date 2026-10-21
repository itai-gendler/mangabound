---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#assignChapters
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#assignChapterRange
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

# Assign chapters

Places selected chapters, or a range of them, in a volume with Assign selected or Assign range. A chapter already in another volume is moved, never duplicated.
