---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User copies the diagnostics in the About tab
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The clipboard holds the versions and the system, and whether the App settings name a working folder, with no path and no name of a book or folder
    kind: product
    actor: user
    entities:
      - entity: app-settings
        effect: reads
        facts:
          - Language
          - Working folder
    contexts:
      desktop:
        place: desktop::app-settings
---

# Copy them for a problem report

## Trigger

The User is about to report a problem.

## Outcome

The report can be pasted into an issue; nothing was sent anywhere.
