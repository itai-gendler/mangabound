---
entities:
  - entity: queue-item
    shows:
      - Name
      - Folders left out
  - entity: library-title
    shows:
      - Name
      - Folders left out
  - entity: chapter-mapping
    shows:
      - Chapters
      - Origin
      - Source
      - Unassigned chapters
  - entity: volume
    shows:
      - Number
      - Chapters
    collects:
      - Number
      - Chapters
  - entity: conversion-options
    shows:
      - One book for the series
      - Online source
    collects:
      - Online source
references:
  - kind: code
    role: implementation
    target: src/renderer/components/mapping/mapping-editor.tsx#MappingEditor
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/mapping-editor.mdx
---

# Volume editor

The chapter mapping of one manga folder or library title: where its chapters come from (File names, Online source or Manual), the chapters and volumes, the ready check, and Confirm mapping.
