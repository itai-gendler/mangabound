---
availability:
  - place: desktop
domain: conversion-options
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/queue-screen.tsx#QueueScreen
  - kind: code
    role: implementation
    target: src/domain/output-profile.ts#withDeviceProfile
  - kind: code
    role: implementation
    target: src/renderer/hooks/use-kept-settings.ts
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/output-profiles.mdx
  - kind: adr
    role: intent
    target: docs/adr/0015-paperwhite-as-the-starting-device.md
---

# Change conversion options

Sets the queue's Steps, Create one book for the series, Device and Format, beside the queue. The choices are kept for the next launch and reach every item that has not set its own.
