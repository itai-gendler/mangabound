---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User checks for updates in the Updates tab
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
  - text: GitHub is asked for the releases, and the newest one after the installed version is shown with the day it was published
    kind: product
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
---

# A new version is out

## Trigger

The User wonders whether the alpha in use is the latest.

## Outcome

The tab says which version is available and when it was published, with Download the update.
