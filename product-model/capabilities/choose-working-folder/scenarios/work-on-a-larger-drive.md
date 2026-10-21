---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses a folder on a larger drive in the Processing tab of App settings
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
  - text: The Product checks that the folder can be used, makes Pending and Scratch in it, and the earlier folder joins the earlier working folders of the App settings
    kind: product
    actor: user
    entities:
      - entity: app-settings
        effect: changes
        facts:
          - Working folder
          - Earlier working folders
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The tab shows both paths and the free space
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

# Work on a larger drive

## Trigger

The system drive is too small for a long series.

## Outcome

The next conversion works in the chosen folder. Books already waiting stay where they are and stay under Ready books, and the app stops looking in an earlier folder once it is empty.
