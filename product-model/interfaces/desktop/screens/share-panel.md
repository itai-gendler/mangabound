---
entities:
  - entity: opds-catalog
    shows:
      - What is shared
      - Network interface
      - Username
      - Password
      - Catalog address
    collects:
      - Network interface
      - Username
      - Password
  - entity: library-folder
    shows:
      - Name
references:
  - kind: code
    role: implementation
    target: src/renderer/components/sharing/share-panel.tsx#SharePanel
  - kind: adr
    role: intent
    target: docs/adr/0016-one-share-panel-fixed-title-bar-clickable-drop-area.md
  - kind: doc
    role: intent
    target: website/src/content/docs/koreader/opds-sharing.mdx
---

# Share to your e-reader

The Share panel of the title bar: what is shared, the network interface, the optional username and password, Start sharing and, while sharing, the catalog address with Copy and Stop sharing.
