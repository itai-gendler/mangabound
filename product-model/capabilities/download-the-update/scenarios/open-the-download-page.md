---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Download the update
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The browser opens on the page of the new release
    kind: product
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
---

# Open the download page

## Trigger

A check found a newer version.

## Outcome

The release page is open; the app does not install anything itself.
