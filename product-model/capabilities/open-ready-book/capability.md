---
availability:
  - place: desktop
domain: ready-books
references:
  - kind: code
    role: implementation
    target: src/main/ipc/artifacts.ts#registerArtifactHandlers
  - kind: adr
    role: intent
    target: docs/adr/0005-product-boundaries-and-anti-goals.md
---

# Open a book

Opens a ready book in the system's default application for its format. Mangabound has no reader of its own.
