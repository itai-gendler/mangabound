---
availability:
  - place: desktop
domain: conversion-options
references:
  - kind: code
    role: implementation
    target: src/domain/item-options.ts#withQueueValue
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#queueReducer
  - kind: code
    role: implementation
    target: src/renderer/components/settings/items-with-options-notice.tsx
  - kind: adr
    role: intent
    target: docs/adr/0047-an-option-of-an-item-is-put-back-to-the-queues.md
---

# Use the queue's options

Takes away options an item set of its own, so that it follows the queue again: one option with Use the queue's value, one item with Use the queue's options, or every item with Use the queue's options for all.
