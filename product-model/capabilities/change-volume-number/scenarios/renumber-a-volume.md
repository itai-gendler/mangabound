---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User changes the number of volume 4 to 3.5
    kind: actor
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Product gives the Volume its new number
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: changes
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Renumber a volume

## Trigger

A special volume sits between two others in the edition the User has.

## Outcome

The volume carries the new number, and its book will be named and ordered by it.

## Edge cases

- A number another volume already has is accepted while editing, and the ready check lists it as an error until one of them changes.
