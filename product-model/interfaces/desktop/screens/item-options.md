---
entities:
  - entity: queue-item
    shows:
      - Name
      - Own options
    collects:
      - Own options
  - entity: library-title
    shows:
      - Name
      - Own options
    collects:
      - Own options
  - entity: conversion-options
    shows:
      - Device
      - Format
      - Custom size
      - Advanced options
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/item-options-screen.tsx#ItemOptionsScreen
  - kind: adr
    role: intent
    target: docs/adr/0046-an-item-can-have-conversion-options-of-its-own.md
---

# Options for an item

The same options for one item or library title alone: what it sets differently from the queue is shown in color, with the queue's value one step away.
