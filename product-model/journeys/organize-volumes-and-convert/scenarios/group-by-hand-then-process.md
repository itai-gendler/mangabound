---
kind: primary
result: achieved
routes:
  desktop: Desktop
steps:
  - text: The User assigns the chapters to the volumes they belong to
    kind: actor
    actor: user
    capability: assign-chapters
    entities:
      - entity: volume
        effect: changes
        facts:
          - Chapters
      - entity: chapter-mapping
        effect: changes
        facts:
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The User confirms the Chapter mapping
    kind: actor
    actor: user
    capability: confirm-chapter-mapping
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Chapter mapping is confirmed and the User is back on the queue
    kind: product
    actor: user
    capability: confirm-chapter-mapping
    entities:
      - entity: chapter-mapping
        effect: changes
        from: Proposed
        to: Confirmed
        facts: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The User presses Process
    kind: actor
    actor: user
    capability: process-queue
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
          - Device
          - Format
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product starts a Pending conversion and makes a Ready book of each Volume
    kind: product
    actor: user
    capability: process-queue
    entities:
      - entity: pending-conversion
        effect: creates
        facts:
          - Made at
          - Books
          - Size
      - entity: ready-book
        effect: creates
        to: Not saved yet
        facts:
          - Name
          - Format
          - Size
          - Title
          - Author
          - Made at
          - Warnings
        with: pending-conversion
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::processing
---

# Group by hand, then process

## Trigger

The editor opened on Manual because no volume was found in the chapter names.

## Outcome

Each confirmed volume is a ready book, and the folder has left the queue.
