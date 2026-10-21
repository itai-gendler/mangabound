---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/domain/mapping-editor.ts#createMappingHistory
  - kind: code
    role: implementation
    target: src/renderer/components/mapping/chapters-from.tsx#ChaptersFrom
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

# Reset mapping edits

Discards every edit made in the editor and returns to the mapping it opened with: Reset all mapping edits, or Start over from the names on the File names tab.
