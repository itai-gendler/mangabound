---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User asks to validate the plan of a queue that holds a library
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
          - One book for the series
    contexts:
      desktop:
        place: desktop::queue
  - text: mangabind reads the library again, and the Product keeps the books of each Library title still to make
    kind: product
    actor: user
    entities:
      - entity: library-title
        effect: reads
        facts:
          - Name
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
  - text: The plan counts the titles and the books they would become
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
---

# Validate the plan of a library

## Trigger

The queue holds a library whose titles are grouped.

## Outcome

The plan lists the books of the titles a run would make, one per volume or one per title in one-book mode; titles already saved are not in it.
