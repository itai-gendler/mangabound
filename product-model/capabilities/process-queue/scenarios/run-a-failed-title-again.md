---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User presses Process again for a library with a failed title
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
  - text: mangabind joins only the failed Library title, not the one already saved
    kind: product
    actor: user
    entities:
      - entity: library-title
        as: failed
        effect: reads
        facts:
          - Name
      - entity: library-title
        as: saved
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::processing
  - text: mangapress converts it into ready books, and the Library title is saved
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
        as: failed
        effect: changes
        from: Failed
        to: Saved
        facts:
          - Failure reason
      - entity: pending-conversion
        effect: changes
        facts:
          - Books
          - Size
    contexts:
      desktop:
        place: desktop::processing
  - text: With every Library title saved, the library leaves the queue
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: removes
        from: Read
      - entity: library-title
        as: failed
        effect: removes
        from: Saved
        with: queue-item
      - entity: library-title
        as: saved
        effect: removes
        from: Saved
        with: queue-item
      - entity: pending-conversion
        effect: changes
        facts:
          - Item results
    contexts:
      desktop:
        place: desktop::results
---

# Run a failed title again

## Trigger

A title of a library failed in the last run and the library is still in the queue.

## Outcome

Only the failed title was joined and converted; now that every title is saved, the library is no longer in the queue.
