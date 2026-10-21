---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User presses Process
    kind: actor
    actor: user
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
  - text: mangabind joins the chapters of each Volume of the confirmed Chapter mapping into a volume file
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
  - text: mangapress converts each joined Volume into a Ready book titled with the series title and the volume number, with the cover chosen for it
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
      - entity: volume
        effect: reads
        facts:
          - Number
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
    contexts:
      desktop:
        place: desktop::processing
  - text: The finished Queue item leaves the queue, and the results show what the run made
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

# Make the books of a manga folder

## Trigger

The queue holds a manga folder whose chapters are grouped into volumes, with both steps on.

## Outcome

Each volume is a book in the chosen format, waiting under Ready books with its warnings, if any; the folder has left the queue and the results offer saving and sharing.

## Edge cases

- Two books of one run that would have the same name get free names instead of replacing each other.
- Several volumes of one title are converted at once, up to Parallel conversions; the items of the queue still run one after another.
- A book that is still packaged after its pages are done shows Saving until it is written.
