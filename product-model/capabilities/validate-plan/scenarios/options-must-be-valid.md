---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User asks to validate the plan while the device is Other with no custom height
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Device
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product refuses until the Conversion options are reviewed
    kind: condition
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Device
          - Custom size
    contexts:
      desktop:
        place: desktop::queue
---

# Options that cannot be used

## Trigger

An option the run would use has a value the converter cannot take.

## Outcome

No plan is made; the message asks to review the output settings before validating.
