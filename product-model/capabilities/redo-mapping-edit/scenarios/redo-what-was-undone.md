---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User redoes the mapping edit just undone
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The chapters are in the Volume again, and off the unassigned ones of the Chapter mapping
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

# Redo an undone assignment

## Trigger

An undo went one step too far.

## Outcome

The edit is back, and undo can reverse it again.
