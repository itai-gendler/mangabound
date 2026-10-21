---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User chooses a folder Mangabound cannot write in
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
  - text: The App settings keep the previous working folder and say why the chosen one cannot be used
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

# A folder that cannot be used

## Trigger

The folder is read-only or on a drive that cannot hold the app's folders.

## Outcome

Nothing moves.
