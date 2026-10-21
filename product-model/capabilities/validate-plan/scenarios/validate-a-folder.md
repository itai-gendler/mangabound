---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User asks to validate the plan
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
          - Device
          - Format
    contexts:
      desktop:
        place: desktop::queue
  - text: mangabind is asked which volume files the Chapter mapping makes, and the Product names the book each Volume becomes in the chosen format
    kind: product
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
      - entity: queue-item
        effect: reads
        facts:
          - Title
      - entity: conversion-options
        effect: reads
        facts:
          - Format
    contexts:
      desktop:
        place: desktop::queue
  - text: The queue shows Plan validated with each book and its pages for the Queue item, and that no library files were written
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

# Validate the plan of a manga folder

## Trigger

The User wants to see the books before spending the time to make them.

## Outcome

Every book the run would make is listed with its name and page count; nothing was written, and the plan stands until the queue, steps or options change.
