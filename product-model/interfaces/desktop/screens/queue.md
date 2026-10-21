---
entities:
  - entity: queue-item
    shows:
      - Kind
      - Name
      - Location
      - Read problem
      - Folders left out
      - Links not followed
      - Own options
  - entity: library-title
    shows:
      - Name
  - entity: chapter-mapping
    shows:
      - Chapters
      - Unassigned chapters
  - entity: volume
    shows:
      - Number
  - entity: conversion-options
    shows:
      - Steps
      - One book for the series
      - Device
      - Format
    collects:
      - Steps
      - One book for the series
      - Device
      - Format
  - entity: pending-conversion
    shows:
      - Made at
      - Books
  - entity: ready-book
    shows:
      - Name
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/queue-screen.tsx#QueueScreen
  - kind: adr
    role: intent
    target: docs/adr/0010-input-queue.md
---

# Queue

The entry screen: the queued items, each with what a run would do with it and why one would be left out; the queue's steps, device and format beside them, with Process and Validate plan; and, under Ready books, the pending conversions from earlier runs.
