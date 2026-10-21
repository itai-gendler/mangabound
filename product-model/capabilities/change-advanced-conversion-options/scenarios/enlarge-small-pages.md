---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User opens Advanced conversion options from the queue
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Device
          - Format
    contexts:
      desktop:
        place: desktop::queue
  - text: The User chooses Fit, enlarging small pages under Page size
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Advanced options
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
---

# Change how pages fill the screen

## Trigger

The last books warned that their pages were smaller than the screen.

## Outcome

Every item that has not set its own page size will be enlarged to the screen, and the choice is kept for the next launch.
