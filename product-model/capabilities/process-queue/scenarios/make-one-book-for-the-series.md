---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User presses Process with Create one book for the series on
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
          - One book for the series
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
  - text: mangabind joins every Volume of the Chapter mapping into one file, with the chapters of each volume under it
    kind: product
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::processing
  - text: 'mangapress makes one Ready book titled with the series title: an EPUB with the volumes and chapters in its table of contents, a CBZ with them as folders, or a PDF with the pages in order'
    kind: product
    actor: user
    entities:
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
      - entity: queue-item
        effect: reads
        facts:
          - Title
          - Author
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::processing
  - text: The finished Queue item leaves the queue, and the results show the one book
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

# Make one book for the series

## Trigger

The User wants a whole series in one book.

## Outcome

One book holds the whole series, its volumes kept as the top level wherever the format can show them.
