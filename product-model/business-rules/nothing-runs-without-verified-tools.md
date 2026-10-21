---
appliesTo:
  - type: capability
    id: process-queue
  - type: capability
    id: validate-plan
  - type: capability
    id: check-conversion-tools
references:
  - kind: code
    role: implementation
    target: src/main/toolchain-bootstrap.ts#bootstrapToolchain
  - kind: adr
    role: intent
    target: docs/adr/0003-bundled-version-pinned-cli-binaries.md
  - kind: adr
    role: intent
    target: docs/adr/0017-bundled-tools-are-updated-by-hand.md
---

# Nothing is converted until the bundled tools pass their check

mangabind and mangapress are checked against the pinned versions, hashes and protocols at every start; until both pass, the queue cannot validate or process anything. The app never downloads or updates them itself.
