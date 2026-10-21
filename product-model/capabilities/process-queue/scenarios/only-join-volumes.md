---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User presses Process with only the grouping step on
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product starts a Pending conversion for this press of Process
    kind: product
    actor: user
    entities:
      - entity: pending-conversion
        effect: creates
        facts:
          - Made at
    contexts:
      desktop:
        place: desktop::processing
  - text: mangabind joins the chapters of each Volume into a CBZ, which becomes a Ready book as it is, without mangapress
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
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
      - entity: pending-conversion
        effect: changes
        facts:
          - Books
          - Size
    contexts:
      desktop:
        place: desktop::processing
  - text: The finished Queue item leaves the queue, and the results say the volumes were joined
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: removes
        from: Read
      - entity: chapter-mapping
        effect: removes
        from: Confirmed
        with: queue-item
      - entity: volume
        effect: removes
        with: chapter-mapping
      - entity: pending-conversion
        effect: changes
        facts:
          - Item results
    contexts:
      desktop:
        place: desktop::results
---

# Only group chapters into volumes

## Trigger

The User wants the joined volumes and will convert them elsewhere or later.

## Outcome

The joined volume CBZs wait under Ready books; no device, format, details or covers were used, and a CBZ in the queue was left out with nothing to join.
