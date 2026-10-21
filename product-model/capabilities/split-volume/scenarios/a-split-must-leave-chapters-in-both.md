---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User asks to split volume 2 before its first chapter
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
  - text: The Product says a split must leave at least one chapter in each Volume, and nothing changes
    kind: condition
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# A split that would leave a volume empty

## Trigger

The chosen chapter is the first one of the volume.

## Outcome

The volume stays as it was.
