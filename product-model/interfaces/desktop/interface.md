---
type: desktop-app
actors:
  - user
references:
  - kind: code
    role: implementation
    target: src/renderer/workflow-app.tsx#WorkflowApp
  - kind: code
    role: implementation
    target: src/main/index.ts
  - kind: adr
    role: context
    target: docs/adr/0001-electron-react-and-module-boundaries.md
  - kind: doc
    role: intent
    target: website/src/content/docs/getting-started/quickstart.mdx
---

# Mangabound desktop

The window where a person adds manga to the queue, organizes volumes, sets book details and conversion options, processes, saves and shares, and opens the app settings. There is no account: everything happens on the person's own computer, in English or Brazilian Portuguese.
