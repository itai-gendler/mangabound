---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User resets all mapping edits
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: Every Volume and the unassigned chapters of the Chapter mapping are as the editor opened with them
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: changes
        facts:
          - Number
          - Chapters
      - entity: chapter-mapping
        effect: changes
        facts:
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Reset all mapping edits

## Trigger

The edits made are not worth keeping.

## Outcome

The mapping is as it was when the editor opened, with no edit left to undo.
