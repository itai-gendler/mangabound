---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User tries to turn off the only step that is on
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
  - text: The step stays on, and the Conversion options say to keep at least one step on
    kind: condition
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
    contexts:
      desktop:
        place: desktop::queue
---

# At least one step stays on

## Trigger

Only one of the two steps is on.

## Outcome

The steps are unchanged.
