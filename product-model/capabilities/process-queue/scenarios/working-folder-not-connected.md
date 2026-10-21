---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User presses Process
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
  - text: The drive of the working folder in App settings is not connected
    kind: condition
    actor: user
    entities:
      - entity: app-settings
        effect: reads
        facts:
          - Working folder
    contexts:
      desktop:
        place: desktop::queue
  - text: Nothing is converted, and the queue says why
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

# The working folder is not connected

## Trigger

The person chose a working folder on a drive that is not connected now.

## Outcome

No conversion starts and nothing is made somewhere else instead; the queue stays as it was until the drive is back or another folder is chosen.
