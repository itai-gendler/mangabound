---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Skip grouping in the editor
    kind: actor
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Conversion options keep only Convert for e-reader, and the User is back on the queue
    kind: product
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Steps
    contexts:
      desktop:
        place: desktop::queue
  - text: The row of the Queue item says it is one book, not grouped
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Kind
          - Name
    contexts:
      desktop:
        place: desktop::queue
---

# Convert the folder as one book

## Trigger

The folder is one volume already, or the User wants its chapters in one book without volumes.

## Outcome

The queue's steps are Convert for e-reader only, so every folder in it is converted whole and a library in it is left out until grouping is on again.
