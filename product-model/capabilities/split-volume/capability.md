---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#splitVolume
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

# Split a volume

Moves a chosen chapter and every later chapter of a volume into a new volume.
