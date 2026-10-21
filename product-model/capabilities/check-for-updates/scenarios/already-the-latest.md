---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User checks for updates
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The tab says the installed version is the latest
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
---

# Already the latest version

## Trigger

No release is newer than the installed one.

## Outcome

Nothing is offered.
