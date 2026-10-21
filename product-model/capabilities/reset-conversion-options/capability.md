---
availability:
  - place: desktop
domain: conversion-options
references:
  - kind: code
    role: implementation
    target: src/renderer/components/settings/reset-options.tsx#ResetOptions
  - kind: code
    role: implementation
    target: src/domain/preferences.ts#defaultPreferences
  - kind: adr
    role: intent
    target: docs/adr/0023-individual-option-resets.md
---

# Reset to defaults

Puts the queue's options back where a first launch starts, all at once or one field at a time with the arrow beside a changed field. Items' own options and the app settings are left alone.
