---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User asks to find the author with MangaDex chosen
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Title
      - entity: conversion-options
        effect: reads
        facts:
          - Online source
    contexts:
      desktop:
        place: desktop::book-details
  - text: MangaDex is searched for the title and answers with the works, their authors and years
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Title
          - Name
    contexts:
      desktop:
        place: desktop::book-details
  - text: The User chooses Use author on the matching work
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        facts:
          - Author
    contexts:
      desktop:
        place: desktop::book-details
---

# Use the author of a match

## Trigger

The User does not know, or does not want to type, who wrote the series.

## Outcome

The author field holds the author of the chosen work, as if it had been typed.
