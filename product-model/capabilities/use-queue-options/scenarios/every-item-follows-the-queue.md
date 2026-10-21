---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User chooses Use the queue's options for all on the Advanced conversion options page
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Own options
      - entity: library-title
        effect: reads
        facts:
          - Own options
      - entity: conversion-options
        effect: reads
        facts:
          - Advanced options
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
  - text: Every Queue item and Library title drops the options it set of its own
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        facts:
          - Own options
      - entity: library-title
        effect: changes
        facts:
          - Own options
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
---

# Every item follows the queue

## Trigger

The notice says several items in the queue are converted with options of their own.

## Outcome

The page says how many items now follow the queue's options.
