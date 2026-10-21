---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User turns off Convert for e-reader
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Steps
    contexts:
      desktop:
        place: desktop::queue
  - text: Device, Format and Advanced conversion options are unavailable, since mangapress will not run
    kind: condition
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
---

# Turn off converting

## Trigger

The User wants only the joined volumes.

## Outcome

A run will join volumes and stop there; a CBZ in the queue says it has nothing to join.
