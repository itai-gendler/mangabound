---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User presses Process for a queue of two manga folders
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
  - text: mangapress fails on one volume of the first Queue item; the ready books it made before the failure are kept
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
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
      - entity: pending-conversion
        effect: changes
        facts:
          - Books
          - Size
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::processing
  - text: The run goes on with the next Queue item
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::processing
  - text: The results say which item could not be converted, and it stays in the queue
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

# An item fails part-way

## Trigger

A conversion fails for one item while others are queued.

## Outcome

The books made before the failure and the other items' books can be saved; the failed item stays in the queue with its message, ready to fix and run again.
