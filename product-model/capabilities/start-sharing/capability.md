---
availability:
  - place: desktop
domain: sharing
references:
  - kind: code
    role: implementation
    target: src/main/ipc/sharing-failure.ts#sharingFailure
  - kind: code
    role: implementation
    target: src/adapters/opds/http-server.ts#NodeOpdsServer
  - kind: adr
    role: intent
    target: docs/adr/0018-opds-basic-auth-only-optionally-blank.md
  - kind: adr
    role: intent
    target: docs/adr/0019-opds-server-binds-a-fixed-port.md
  - kind: adr
    role: intent
    target: docs/adr/0022-remember-chosen-network-interface.md
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

# Start sharing

Serves the OPDS catalog on the network interface the User picks, at port 48123, with an optional username and password, until sharing is stopped or the app closes.
