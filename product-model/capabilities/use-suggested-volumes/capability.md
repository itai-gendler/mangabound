---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#applyVolumeSuggestion
  - kind: code
    role: implementation
    target: src/adapters/metadata-providers/mangadex/provider.ts#MangaDexProvider
  - kind: adr
    role: intent
    target: docs/adr/0013-online-sources-for-volume-data.md
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

# Use these volumes

Applies a work's volumes from the online source to the chapters of the folder, by chapter number, and records where they came from.
