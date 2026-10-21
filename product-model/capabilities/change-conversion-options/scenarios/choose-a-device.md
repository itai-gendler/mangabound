---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses a Kobo Libra Colour as the device
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Device
    contexts:
      desktop:
        place: desktop::queue
  - text: The Conversion options also put upscaling and color back to where that device starts
    kind: product
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Advanced options
    contexts:
      desktop:
        place: desktop::queue
---

# Choose another device

## Trigger

The User converts for another e-reader than before.

## Outcome

The device is kept for the next launch; enlarging small pages and keeping color now follow the new device, and every other option stays as it was.
