---
availability:
  - place: desktop
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#validateMapping
  - kind: code
    role: implementation
    target: src/application/workflows/input-sessions.ts#InputSessions
  - kind: code
    role: implementation
    target: src/adapters/mangabind/stored-details.ts#carryStoredDetails
  - kind: adr
    role: intent
    target: docs/adr/0008-mapping-starts-from-mangabind-grouping.md
  - kind: adr
    role: intent
    target: docs/adr/0012-libraries-in-the-queue.md
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

# Confirm mapping

Accepts the volumes in the editor as the item's grouping, gaps included, once the ready check lists no errors. For a library title, the grouping is written into its folder's mangabind.json at once and the library is read again.
