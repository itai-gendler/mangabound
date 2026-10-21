---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User merges volume 6 into volume 5
    kind: actor
    actor: user
    entities:
      - entity: volume
        as: target
        effect: reads
        facts:
          - Number
      - entity: volume
        as: source
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The chapters of the source Volume join the target Volume, and the source is removed
    kind: product
    actor: user
    entities:
      - entity: volume
        as: target
        effect: changes
        facts:
          - Chapters
      - entity: volume
        as: source
        effect: removes
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Merge into the previous volume

## Trigger

Two volumes of the proposal are one volume in the User's edition.

## Outcome

One volume holds the chapters of both.
