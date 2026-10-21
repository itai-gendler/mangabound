---
entities:
  - entity: conversion-options
    shows:
      - Device
      - Format
      - Custom size
      - Advanced options
      - One book for the series
    collects:
      - Device
      - Format
      - Custom size
      - Advanced options
  - entity: queue-item
    shows:
      - Own options
  - entity: library-title
    shows:
      - Own options
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/conversion-options-screen.tsx#ConversionOptionsScreen
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/output-profiles.mdx
  - kind: adr
    role: intent
    target: docs/adr/0036-page-layout-options-are-grouped-by-decision.md
---

# Advanced conversion options

The queue's conversion options in full, grouped as Reading, Double-page spreads, Size and borders, Cropping, Two-page view, Color and tone, Page images, Cover and Book metadata, with how many items have options of their own.
