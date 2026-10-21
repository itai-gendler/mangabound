---
availability:
  - place: desktop
domain: conversion-options
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/conversion-options-screen.tsx#ConversionOptionsScreen
  - kind: code
    role: implementation
    target: src/domain/output-profile.ts#validateMangapressSettings
  - kind: code
    role: implementation
    target: src/domain/output-profile.ts#pageLayoutLocks
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/advanced-options/index.mdx
  - kind: adr
    role: intent
    target: docs/adr/0037-image-options-color-follows-the-device.md
  - kind: adr
    role: intent
    target: docs/adr/0050-stretch-wins-over-crop-to-fill.md
---

# Change advanced conversion options

Sets any of mangapress's options for the whole queue on the Advanced conversion options page, grouped by purpose. An option another choice makes useless stays visible, dimmed, with the reason, and keeps its value.
