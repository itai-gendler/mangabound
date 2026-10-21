---
availability:
  - place: desktop
domain: sharing
references:
  - kind: code
    role: implementation
    target: src/main/ipc/opds.ts#registerOpdsHandlers
  - kind: code
    role: implementation
    target: src/renderer/components/sharing/share-panel.tsx#SharePanel
  - kind: doc
    role: intent
    target: website/src/content/docs/koreader/opds-sharing.mdx
---

# Stop sharing

Ends the OPDS catalog at once; a download in progress is cut off.
