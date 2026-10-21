---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User resets the Advanced conversion options page to its defaults
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Own options
      - entity: conversion-options
        effect: reads
        facts:
          - Format
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
  - text: The format and options of the Conversion options are back at their defaults; what each Queue item set of its own stays
    kind: product
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Format
          - Custom size
          - Advanced options
      - entity: queue-item
        effect: reads
        facts:
          - Own options
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
---

# Reset the Advanced conversion options page

## Trigger

Some items have options of their own, and the queue's should start over.

## Outcome

The queue's format and options are the defaults; the steps, the one-book choice and the items' own options are unchanged.
