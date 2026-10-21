---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User undoes the last mapping edit
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Volume is back as it was before the assignment, and the chapters are unassigned again in the Chapter mapping
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

# Undo the last assignment

## Trigger

The last assignment went to the wrong volume.

## Outcome

The mapping is as it was before that edit, and the edit can be redone.
