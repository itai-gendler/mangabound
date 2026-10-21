---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User types 2a as the new Volume number and adds it
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
  - text: The Product says the volume number is invalid, and nothing is added
    kind: condition
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
---

# A number that is not a volume number

## Trigger

The number typed is not whole or decimal, or is above 100000.

## Outcome

No volume is created; the editor says the number is invalid and the mapping is as it was.
