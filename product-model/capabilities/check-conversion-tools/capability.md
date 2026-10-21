---
availability:
  - place: desktop
references:
  - kind: code
    role: implementation
    target: src/main/toolchain-bootstrap.ts#bootstrapToolchain
  - kind: code
    role: implementation
    target: src/adapters/toolchain/verification.ts
  - kind: adr
    role: intent
    target: docs/adr/0003-bundled-version-pinned-cli-binaries.md
---

# Check the conversion tools

At every start, Mangabound checks that the bundled mangabind and mangapress are the pinned ones before anything can be converted, and shows the result in the About tab.
