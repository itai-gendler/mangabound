---
entities:
  - entity: pending-conversion
    shows:
      - Item results
      - Books
  - entity: ready-book
    shows:
      - Name
      - Format
      - Size
      - Warnings
      - Saved to
  - entity: conversion-options
    shows:
      - Device
      - Format
  - entity: queue-item
    shows:
      - Name
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/results-screen.tsx#ResultsScreen
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/exporting.mdx
---

# Results

What a run, or an earlier pending conversion, came to: the ready books with their state and actions, the items that failed or were left out with Fix where it helps, the warnings about the books, and Send to KOReader.
