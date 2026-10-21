---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User opens the conversion options for one CBZ of the queue
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
          - Own options
      - entity: conversion-options
        effect: reads
        facts:
          - Format
    contexts:
      desktop:
        place: desktop::queue
  - text: The User chooses EPUB as its format
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        facts:
          - Own options
    contexts:
      desktop:
        place: desktop::item-options
  - text: The format shows in color as the Queue item's own, and every other option follows the Conversion options of the queue
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Own options
      - entity: conversion-options
        effect: reads
        facts:
          - Device
          - Format
    contexts:
      desktop:
        place: desktop::item-options
---

# Make one item an EPUB

## Trigger

One item should be made differently from the rest of the queue.

## Outcome

Its row shows that it has options of its own; a later change to the queue's device still reaches it. Its own options last until the app closes.
