---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User selects the first two chapters and chooses volume 1
    kind: actor
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The User assigns the selected chapters
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Product puts the chapters in the Volume and takes them off the unassigned ones of the Chapter mapping
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: changes
        facts:
          - Chapters
      - entity: chapter-mapping
        effect: changes
        facts:
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Assign selected chapters

## Trigger

The User builds volumes by hand.

## Outcome

Volume 1 holds the two chapters; the selection is cleared for the next assignment.
