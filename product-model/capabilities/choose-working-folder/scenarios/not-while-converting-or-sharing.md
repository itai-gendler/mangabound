---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User chooses a working folder while a conversion runs
    kind: actor
    actor: user
    entities:
      - entity: app-settings
        effect: reads
        facts:
          - Working folder
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The App settings keep the folder as it was, and say it cannot change while a conversion or a share is running
    kind: condition
    actor: user
    entities:
      - entity: app-settings
        effect: reads
        facts:
          - Working folder
    contexts:
      desktop:
        place: desktop::app-settings
---

# Not while converting or sharing

## Trigger

A run or a share is using the working folder.

## Outcome

The working folder is unchanged; it can be changed once the run ends or sharing stops.
