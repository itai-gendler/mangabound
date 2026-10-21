---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: Mangabound starts and one bundled tool is not the pinned one
    kind: condition
    unattended: true
    entities: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The queue shows that conversion is unavailable until the bundled tools are restored, and its actions stay disabled
    kind: product
    entities: []
    contexts:
      desktop:
        place: desktop::queue
---

# A tool fails the check

## Trigger

A tool was changed or is missing after installation.

## Outcome

Nothing can be validated or processed; the About tab says which tool did not pass, and reinstalling Mangabound restores it.
