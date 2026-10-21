---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User presses Process for a queue that holds a CBZ
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Device
          - Format
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
  - text: mangapress converts the CBZ of the Queue item into one Ready book, with its own details and cover
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Title
          - Author
          - Language
      - entity: book-cover
        effect: reads
        facts:
          - Book
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
  - text: The finished Queue item leaves the queue
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: removes
        from: Read
      - entity: pending-conversion
        effect: changes
        facts:
          - Item results
    contexts:
      desktop:
        place: desktop::results
---

# Convert a CBZ straight for the e-reader

## Trigger

The queue holds a complete volume as a CBZ.

## Outcome

The volume is one book for the chosen device and format, without any grouping step.
