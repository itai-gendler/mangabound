---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User creates volume 1 in a Chapter mapping that has no volumes yet
    kind: actor
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
          - Unassigned chapters
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Product adds an empty Volume numbered 1 and offers 2 for the next one
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: creates
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Create the first volume

## Trigger

No volume was found in the chapter names, and the editor opened on Manual.

## Outcome

Volume 1 exists with no chapters, ready to take some; until it does, the ready check lists it as an error.
