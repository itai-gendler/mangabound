---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User chooses Other as the device and fills in only Custom width
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Device
          - Custom size
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
  - text: The page says both Custom width and Custom height are needed, and a run refuses the Conversion options until they are
    kind: condition
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Custom size
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
---

# The Other device needs a size

## Trigger

The e-reader is not one of the listed devices.

## Outcome

Nothing can be validated or processed for this device until both dimensions are filled in.
