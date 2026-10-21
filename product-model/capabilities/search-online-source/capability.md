---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/adapters/metadata-providers/mangadex/provider.ts#MangaDexProvider
  - kind: code
    role: implementation
    target: src/main/ipc/metadata.ts#registerMetadataHandlers
  - kind: adr
    role: intent
    target: docs/adr/0013-online-sources-for-volume-data.md
  - kind: doc
    role: intent
    target: docs/adding-a-metadata-provider.md
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

# Search an online source

Looks a manga up by its title in an online source the User picks, MangaDex for now, to find the work whose volumes to use. Nothing is sent until the User searches, and only the title goes.
