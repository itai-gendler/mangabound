---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User presses Process for a queue that holds a library
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
  - text: mangabind joins the grouped Library title and leaves out the one that needs volumes
    kind: product
    actor: user
    entities:
      - entity: library-title
        as: grouped
        effect: reads
        facts:
          - Name
      - entity: library-title
        as: ungrouped
        effect: reads
        facts:
          - Name
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::processing
  - text: mangapress converts the grouped Library title into ready books with its own details and options, and the title is saved
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
      - entity: library-title
        as: grouped
        effect: changes
        from: Grouped
        to: Saved
        facts: []
      - entity: pending-conversion
        effect: changes
        facts:
          - Books
          - Size
    contexts:
      desktop:
        place: desktop::processing
  - text: The results report the Library title left out until it is grouped, and the Queue item stays in the queue
    kind: product
    actor: user
    entities:
      - entity: pending-conversion
        effect: changes
        facts:
          - Item results
      - entity: library-title
        as: ungrouped
        effect: reads
        facts:
          - Name
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
---

# Make the books of a library

## Trigger

The queue holds a library with one title grouped and one that still needs volumes.

## Outcome

The grouped title's books wait under Ready books and the title shows Saved; the other title is reported as left out, and the library stays in the queue until every title is saved.

## Edge cases

- The titles of a library are made one after another, each with the details and options set for it.
