---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User presses Process for a manga folder whose volumes were edited
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
      - entity: volume
        effect: reads
        facts:
          - Number
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
  - text: The Chapter mapping differs from the grouping mangabind proposed, so it is to be written into the folder's mangabind.json before joining
    kind: condition
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
  - text: The folder cannot be written, so the Queue item fails before anything is joined
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
          - Location
    contexts:
      desktop:
        place: desktop::results
---

# Edited volumes cannot be kept with the folder

## Trigger

The folder holding the chapters is read-only, or its mangabind.json is not valid JSON.

## Outcome

Nothing is made of that folder; the results say mangabind.json could not be saved in the source folder, the folder stays in the queue, and the other items still run.
