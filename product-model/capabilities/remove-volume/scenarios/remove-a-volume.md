---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User removes volume 3
    kind: actor
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Product removes the Volume and its chapters become unassigned in the Chapter mapping
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: removes
      - entity: chapter-mapping
        effect: changes
        facts:
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Remove a volume with chapters

## Trigger

A volume was created by mistake, or is to be rebuilt.

## Outcome

The volume is gone and its chapters are listed as unassigned, ready to be placed elsewhere.
