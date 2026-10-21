---
availability:
  - place: desktop
domain: ready-books
references:
  - kind: code
    role: implementation
    target: src/renderer/components/sharing/send-to-koreader.tsx#SendToKoreader
  - kind: code
    role: implementation
    target: src/main/ipc/sharing-target.ts#sharingTarget
  - kind: doc
    role: intent
    target: website/src/content/docs/koreader/opds-sharing.mdx
---

# Share these books

Offers the ready books to KOReader from the results, with Send to KOReader: it makes them what sharing serves and opens the Share panel. They need not be saved first.
