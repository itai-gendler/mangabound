---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User resets the conversion options to their defaults beside the queue
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
  - text: The Conversion options are back to both steps, no single book for the series, a Kindle Paperwhite, CBZ and the starting options
    kind: product
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Steps
          - One book for the series
          - Device
          - Format
          - Custom size
          - Advanced options
    contexts:
      desktop:
        place: desktop::queue
---

# Reset everything beside the queue

## Trigger

The User has lost track of what was changed.

## Outcome

Everything is as on a first launch; the chosen online source and the app settings did not change.
