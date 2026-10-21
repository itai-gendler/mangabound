---
availability:
  - place: desktop
domain: conversion-options
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/item-options-screen.tsx#ItemOptionsScreen
  - kind: code
    role: implementation
    target: src/domain/item-options.ts#itemOptionsFor
  - kind: code
    role: implementation
    target: src/domain/item-options.ts#effectiveOptions
  - kind: adr
    role: intent
    target: docs/adr/0046-an-item-can-have-conversion-options-of-its-own.md
  - kind: adr
    role: intent
    target: docs/adr/0049-the-queue-page-says-which-items-have-their-own.md
---

# Edit an item's conversion options

Gives one queue item, or one library title, conversion options of its own on the same page as the queue's; it keeps following the queue for every option it does not set.
