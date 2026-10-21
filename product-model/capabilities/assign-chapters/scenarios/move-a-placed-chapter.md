---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User selects a chapter of volume 3 and assigns it to volume 4
    kind: actor
    actor: user
    entities:
      - entity: volume
        as: from
        effect: reads
        facts:
          - Number
          - Chapters
      - entity: volume
        as: to
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The chapter leaves the first Volume and joins the second
    kind: product
    actor: user
    entities:
      - entity: volume
        as: from
        effect: changes
        facts:
          - Chapters
      - entity: volume
        as: to
        effect: changes
        facts:
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Move a chapter that is already placed

## Trigger

A chapter belongs to the next volume in the User's edition.

## Outcome

The chapter is in volume 4 only.

## Edge cases

- A chapter whose name says volume 3 is kept there by mangabind, so the ready check lists the move as an error.
