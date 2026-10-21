---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User presses Process for a queue that holds a library of two grouped titles
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
  - text: Joining one Library title makes nothing, and it fails with the reason
    kind: product
    actor: user
    entities:
      - entity: library-title
        as: failing
        effect: changes
        from: Grouped
        to: Failed
        facts:
          - Failure reason
    contexts:
      desktop:
        place: desktop::processing
  - text: mangapress still converts the other Library title, which is saved
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
        as: other
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
  - text: The results tell the two titles apart, and the Queue item stays with the failed title to run again
    kind: product
    actor: user
    entities:
      - entity: pending-conversion
        effect: changes
        facts:
          - Item results
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
---

# A title of a library fails

## Trigger

One title of a library cannot be made in a run.

## Outcome

The other title's books are ready; the failed one shows Failed with its reason and runs again on the next Process.
