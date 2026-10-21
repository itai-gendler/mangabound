---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Use the default folder
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
  - text: The working folder of the App settings is Chosen by Mangabound again, and the chosen folder joins the earlier working folders
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
---

# Go back to the default places

## Trigger

The drive of the chosen folder is gone for good, or no longer needed.

## Outcome

The next conversion works in the default places; books still waiting in the old folder stay listed until they are saved or deleted.
