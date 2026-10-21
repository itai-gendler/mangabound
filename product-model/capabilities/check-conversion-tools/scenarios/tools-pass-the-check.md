---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: Mangabound starts and checks the versions, hashes and protocols of the bundled tools
    kind: condition
    unattended: true
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The About tab lists mangabind and mangapress as verified, and the queue can process
    kind: product
    entities: []
    contexts:
      desktop:
        place: desktop::app-settings
---

# The tools pass the check

## Trigger

The app starts.

## Outcome

Conversion is available with the pinned tools.
